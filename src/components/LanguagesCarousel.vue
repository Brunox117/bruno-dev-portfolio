<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue';
import ReactLogo from '@/assets/svgs/ReactLogo.vue';
import FlutterLogo from '@/assets/svgs/FlutterLogo.vue';
import VueLogo from '@/assets/svgs/VueLogo.vue';
import TypeScript from '@/assets/svgs/TypeScript.vue';
import FirebaseLogo from '@/assets/svgs/FirebaseLogo.vue';
import GitLogo from '@/assets/svgs/GitLogo.vue';
import DartLogo from '@/assets/svgs/DartLogo.vue';

const baseLogos = [
  { component: ReactLogo, name: 'React' },
  { component: FlutterLogo, name: 'Flutter' },
  { component: VueLogo, name: 'Vue' },
  { component: TypeScript, name: 'TypeScript' },
  { component: FirebaseLogo, name: 'Firebase' },
  { component: GitLogo, name: 'Git' },
  { component: DartLogo, name: 'Dart' },
];

// Duplicate the logos array to create a seamless loop
const carouselLogos = [...baseLogos, ...baseLogos];

const carouselRef = ref<HTMLElement | null>(null);
const scrollInterval = ref<number | null>(null);
const scrollSpeed = 2; // Increased speed for better visibility

const startInfiniteScroll = () => {
  if (!carouselRef.value) return;

  scrollInterval.value = window.setInterval(() => {
    if (!carouselRef.value) return;

    carouselRef.value.scrollLeft += scrollSpeed;

    // Reset scroll position when reaching the middle
    if (carouselRef.value.scrollLeft >= carouselRef.value.scrollWidth / 2) {
      carouselRef.value.scrollLeft = 0;
    }
  }, 20); // Reduced interval for smoother animation
};

onMounted(() => {
  startInfiniteScroll();
});

onUnmounted(() => {
  if (scrollInterval.value) {
    clearInterval(scrollInterval.value);
  }
});
</script>

<template>
  <div class="relative w-full max-w-3xl mx-auto overflow-hidden flex justify-center">
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
      <div v-for="(logo, index) in carouselLogos" :key="index" class="flex-shrink-0">
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
