<script setup lang="ts">
import { ref, onMounted } from 'vue';

const mobileMenu = ref<HTMLElement | null>(null);
const mobileMenuButton = ref<HTMLButtonElement | null>(null);

onMounted(() => {
  // Script para el menú móvil
  mobileMenuButton.value?.addEventListener('click', () => {
    mobileMenu.value?.classList.toggle('hidden');
  });

  // Cerrar menú móvil al hacer click en un enlace
  document.querySelectorAll('#mobile-menu a').forEach((link) => {
    link.addEventListener('click', () => {
      mobileMenu.value?.classList.add('hidden');
    });
  });

  // Actualizar año en el footer
  const yearElement = document.getElementById('year');
  if (yearElement) {
    yearElement.textContent = new Date().getFullYear().toString();
  }
});
</script>
<template>
  <!-- Header y Navegación -->
  <header
    class="bg-slate-900/80 backdrop-blur-sm fixed top-0 left-0 right-0 z-50 border-b border-slate-700"
  >
    <div class="container mx-auto px-6 py-4 flex justify-between items-center">
      <a
        href="#home"
        class="text-2xl font-bold font-mono text-blue-400 hover:text-blue-300 transition-colors"
        >Bruno Jiménez</a
      >
      <nav class="hidden md:flex space-x-8">
        <a href="#home" class="text-gray-300 hover:text-blue-400 transition-colors">Inicio</a>
        <a href="#experience" class="text-gray-300 hover:text-blue-400 transition-colors"
          >Experiencia</a
        >
        <a href="#projects" class="text-gray-300 hover:text-blue-400 transition-colors"
          >Proyectos</a
        >
        <a href="#courses" class="text-gray-300 hover:text-blue-400 transition-colors">Cursos</a>
      </nav>
      <button
        ref="mobileMenuButton"
        id="mobile-menu-button"
        class="md:hidden text-gray-300 focus:outline-none"
      >
        <svg
          class="w-6 h-6"
          fill="none"
          stroke="currentColor"
          viewBox="0 0 24 24"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            stroke-linecap="round"
            stroke-linejoin="round"
            stroke-width="2"
            d="M4 6h16M4 12h16m-7 6h7"
          ></path>
        </svg>
      </button>
    </div>
    <!-- Menú Móvil -->
    <div ref="mobileMenu" id="mobile-menu" class="hidden md:hidden px-6 pb-4">
      <a href="#home" class="block py-2 text-gray-300 hover:text-blue-400">Inicio</a>
      <a href="#projects" class="block py-2 text-gray-300 hover:text-blue-400">Proyectos</a>
      <a href="#courses" class="block py-2 text-gray-300 hover:text-blue-400">Cursos</a>
    </div>
  </header>
</template>
