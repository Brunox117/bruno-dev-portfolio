<script setup lang="ts">
const experience = [
  {
    title: 'Senior Developer',
    company: 'Tech Company',
    period: '2020 - Present',
    description: 'Led development of multiple web applications using Vue.js and Node.js',
  },
  {
    title: 'Full Stack Developer',
    company: 'Digital Agency',
    period: '2018 - 2020',
    description: 'Developed and maintained client websites and web applications',
  },
];

const projects = [
  {
    title: 'E-commerce Platform',
    description: 'Built with Vue.js and Node.js',
    technologies: ['Vue.js', 'Node.js', 'MongoDB'],
  },
  {
    title: 'Task Management App',
    description: 'Real-time task management application',
    technologies: ['React', 'Firebase', 'Tailwind CSS'],
  },
];

const courses = [
  {
    title: 'Advanced Web Development',
    platform: 'Udemy',
    year: '2023',
  },
  {
    title: 'Cloud Architecture',
    platform: 'AWS',
    year: '2022',
  },
];
</script>

<template>
  <div class="min-h-screen bg-gradient-to-br from-slate-900 to-slate-800 text-gray-100">
    <!-- Header Section -->
    <header class="container mx-auto px-6 py-16">
      <div class="max-w-4xl mx-auto">
        <h1 class="text-5xl font-bold mb-6 text-blue-400 font-mono">Bruno Jiménez</h1>
        <p class="text-xl text-gray-300 font-light leading-relaxed">
          Full Stack Developer passionate about creating elegant solutions to complex problems.
          Specialized in modern web technologies and cloud architecture.
        </p>
      </div>
    </header>

    <!-- Experience Section -->
    <section class="container mx-auto px-6 py-16 bg-slate-800/50">
      <div class="max-w-4xl mx-auto">
        <h2 class="text-3xl font-bold mb-8 text-orange-400 font-mono">Experience</h2>
        <div class="space-y-8">
          <div
            v-for="(job, index) in experience"
            :key="index"
            class="bg-slate-700/50 p-6 rounded-lg hover:bg-slate-700/70 transition-all"
          >
            <h3 class="text-xl font-bold text-blue-400">{{ job.title }}</h3>
            <p class="text-orange-300">{{ job.company }} | {{ job.period }}</p>
            <p class="mt-2 text-gray-300">{{ job.description }}</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Projects Section -->
    <section class="container mx-auto px-6 py-16">
      <div class="max-w-4xl mx-auto">
        <h2 class="text-3xl font-bold mb-8 text-orange-400 font-mono">Projects</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
          <div
            v-for="(project, index) in projects"
            :key="index"
            class="bg-slate-700/50 p-6 rounded-lg hover:bg-slate-700/70 transition-all"
          >
            <h3 class="text-xl font-bold text-blue-400">{{ project.title }}</h3>
            <p class="mt-2 text-gray-300">{{ project.description }}</p>
            <div class="mt-4 flex flex-wrap gap-2">
              <span
                v-for="tech in project.technologies"
                :key="tech"
                class="px-3 py-1 bg-orange-500/20 text-orange-300 rounded-full text-sm"
              >
                {{ tech }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Courses Section -->
    <section class="container mx-auto px-6 py-16 bg-slate-800/50">
      <div class="max-w-4xl mx-auto">
        <h2 class="text-3xl font-bold mb-8 text-orange-400 font-mono">Courses & Certifications</h2>
        <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
          <div
            v-for="(course, index) in courses"
            :key="index"
            class="bg-slate-700/50 p-6 rounded-lg hover:bg-slate-700/70 transition-all"
          >
            <h3 class="text-xl font-bold text-blue-400">{{ course.title }}</h3>
            <p class="text-orange-300">{{ course.platform }}</p>
            <p class="text-gray-300">{{ course.year }}</p>
          </div>
        </div>
      </div>
    </section>
  </div>
</template>

<style scoped></style>
