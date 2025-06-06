<script setup lang="ts">
import ReactLogo from '@/assets/svgs/ReactLogo.vue';
import CoursesComponent from '@/components/CoursesComponent.vue';
import ExperienceComponent from '@/components/ExperienceComponent.vue';
import IntroComponent from '@/components/IntroComponent.vue';
import LanguagesCarousel from '@/components/LanguagesCarousel.vue';
import ProjectsComponent from '@/components/ProjectsComponent.vue';
</script>

<template>
  <body class="bg-slate-900 text-gray-300">
    <main id="home" class="container mx-auto px-6 pt-24">
      <IntroComponent />
      <ExperienceComponent />
      <ProjectsComponent />
      <CoursesComponent />
    </main>
  </body>
</template>

<style></style>
