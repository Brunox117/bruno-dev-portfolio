<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';
import ReactLogo from '@/assets/svgs/ReactLogo.vue';
import FlutterLogo from '@/assets/svgs/FlutterLogo.vue';
import VueLogo from '@/assets/svgs/VueLogo.vue';
import TypeScript from '@/assets/svgs/TypeScript.vue';
import FirebaseLogo from '@/assets/svgs/FirebaseLogo.vue';
import GitLogo from '@/assets/svgs/GitLogo.vue';

// Array de logos (por ahora solo React, pero se pueden agregar más)
const baseLogos = [
  { component: ReactLogo, name: 'React' },
  { component: FlutterLogo, name: 'Flutter' },
  { component: VueLogo, name: 'Vue' },
  { component: TypeScript, name: 'TypeScript' },
  { component: FirebaseLogo, name: 'Firebase' },
  { component: GitLogo, name: 'Git' },
];

// Duplicamos los logos para crear el efecto infinito
const logos = [...baseLogos, ...baseLogos, ...baseLogos];

const carouselRef = ref<HTMLElement | null>(null);
const scrollInterval = ref<number | null>(null);
const isHovered = ref(false);
const isScrolling = ref(false);

// Función para iniciar el scroll automático
const startAutoScroll = () => {
  if (scrollInterval.value) return;

  scrollInterval.value = window.setInterval(() => {
    if (carouselRef.value && !isHovered.value && !isScrolling.value) {
      carouselRef.value.scrollLeft += 1;

      // Cuando llegamos al final del segundo conjunto de logos
      if (carouselRef.value.scrollLeft >= (carouselRef.value.scrollWidth / 3) * 2) {
        isScrolling.value = true;
        // Hacemos un scroll suave al inicio del segundo conjunto
        carouselRef.value.scrollTo({
          left: carouselRef.value.scrollWidth / 3,
          behavior: 'auto',
        });
        setTimeout(() => {
          isScrolling.value = false;
        }, 50);
      }
    }
  }, 30);
};

// Función para detener el scroll automático
const stopAutoScroll = () => {
  if (scrollInterval.value) {
    clearInterval(scrollInterval.value);
    scrollInterval.value = null;
  }
};

onMounted(() => {
  if (carouselRef.value) {
    // Iniciamos el scroll desde el segundo conjunto de logos
    carouselRef.value.scrollLeft = carouselRef.value.scrollWidth / 3;
  }
  startAutoScroll();
});

onUnmounted(() => {
  stopAutoScroll();
});
</script>

<template>
  <div
    class="relative w-full max-w-3xl mx-auto overflow-hidden"
    @mouseenter="isHovered = true"
    @mouseleave="isHovered = false"
  >
    <!-- Fade effect on the left -->
    <div
      class="absolute left-0 top-0 bottom-0 w-20 bg-gradient-to-r from-slate-900 to-transparent z-10"
    ></div>

    <!-- Fade effect on the right -->
    <div
      class="absolute right-0 top-0 bottom-0 w-20 bg-gradient-to-l from-slate-900 to-transparent z-10"
    ></div>

    <!-- Carousel container -->
    <div
      ref="carouselRef"
      class="flex space-x-8 py-4 overflow-x-auto scrollbar-hide"
      style="scroll-behavior: smooth"
    >
      <div v-for="(logo, index) in logos" :key="index" class="flex-shrink-0">
        <component :is="logo.component" />
      </div>
    </div>
  </div>
</template>

<style scoped>
/* Hide scrollbar for Chrome, Safari and Opera */
.scrollbar-hide::-webkit-scrollbar {
  display: none;
}

/* Hide scrollbar for IE, Edge and Firefox */
.scrollbar-hide {
  -ms-overflow-style: none; /* IE and Edge */
  scrollbar-width: none; /* Firefox */
}
</style>
