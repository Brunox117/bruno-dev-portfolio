<script setup lang="ts">
import TagComponent from './TagComponent.vue';
</script>

<template>
  <!-- Sección 3: Proyectos -->
  <section id="projects" class="py-20">
    <h2 class="text-4xl font-bold text-center mb-12">
      Mis <span class="text-blue-400">Proyectos</span>
    </h2>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      <!-- Proyecto 1 -->
      <div class="card-border-gradient transition-all hover:shadow-2xl hover:scale-105">
        <div class="card-content">
          <h3 class="text-2xl font-bold mb-4 text-blue-400 font-mono">Punto de venta</h3>
          <p class="text-gray-400 mb-6">Prueba de concepto de landing page para Punto de Venta</p>
          <div class="flex flex-wrap gap-2 mb-6">
            <TagComponent name="React" />
            <TagComponent name="Firebase" />
            <TagComponent name="Tailwind" />
          </div>
          <div class="flex space-x-4">
            <a
              href="https://puntodeventaabarrotes.netlify.app/"
              class="text-blue-400 hover:text-blue-300 transition-colors"
              >Ver Demo</a
            >
          </div>
        </div>
      </div>

      <!-- Proyecto 2 -->
      <div class="card-border-gradient transition-all hover:shadow-2xl hover:scale-105">
        <div class="card-content relative">
          <div class="flex justify-between items-center mb-4">
            <h3 class="text-2xl font-bold text-blue-400 font-mono">Carreer mode tracker</h3>
            <span class="bg-blue-400/10 text-yellow-300 text-sm font-mono px-3 py-1 rounded-full"
              >En construcción</span
            >
          </div>
          <p class="text-gray-400 mb-6">
            Aplicación para llevar las estadísticas del modo carrera de FC25 tanto de jugadores y
            clubes así como estadísticas generales de manager. Construída con Flutter, usando
            Riverpod, GoRouter, etc.
          </p>
          <div class="flex flex-wrap gap-2 mb-6">
            <TagComponent name="Flutter" />
          </div>
          <div class="flex space-x-4">
            <!-- <a
              href="https://puntodeventaabarrotes.netlify.app/"
              class="text-blue-400 hover:text-blue-300 transition-colors"
              >Ver código</a
            > -->
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
