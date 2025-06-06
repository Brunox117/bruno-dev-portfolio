<script setup lang="ts">
import { ref, onMounted } from 'vue';

const mobileMenu = ref(null);
const mobileMenuButton = ref(null);

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
    yearElement.textContent = new Date().getFullYear();
  }
});
</script>

<template>
  <body class="bg-slate-900 text-gray-300">
    <main class="container mx-auto px-6 pt-24">
      <!-- Sección 1: Home -->
      <section id="home" class="min-h-screen flex items-center justify-center text-center">
        <div class="max-w-3xl">
          <h1 class="text-5xl md:text-7xl font-bold mb-4">
            Hola, soy <span class="text-blue-400">[Tu Nombre]</span>
          </h1>
          <p class="text-xl md:text-2xl text-gray-400 mb-8 font-mono">
            [Tu Título o Rol - ej. Desarrollador Web Full-Stack]
          </p>
          <p class="text-lg mb-8 max-w-2xl mx-auto">
            Aquí puedes escribir una breve biografía sobre ti. Habla de tu pasión por la tecnología,
            las herramientas que te gustan y lo que estás buscando profesionalmente. Sé breve pero
            impactante.
          </p>
          <div class="flex justify-center space-x-6">
            <a
              href="[Tu URL de LinkedIn]"
              target="_blank"
              class="text-gray-400 hover:text-blue-400 transition-colors"
            >
              <svg class="w-8 h-8" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                <path
                  fill-rule="evenodd"
                  d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"
                  clip-rule="evenodd"
                />
              </svg>
            </a>
            <a
              href="[Tu URL de GitHub]"
              target="_blank"
              class="text-gray-400 hover:text-blue-400 transition-colors"
            >
              <svg class="w-8 h-8" fill="currentColor" viewBox="0 0 24 24" aria-hidden="true">
                <path
                  fill-rule="evenodd"
                  d="M12 2C6.477 2 2 6.477 2 12c0 4.418 2.865 8.168 6.839 9.492.5.092.682-.217.682-.482 0-.237-.009-.868-.014-1.703-2.782.605-3.369-1.343-3.369-1.343-.454-1.158-1.11-1.466-1.11-1.466-.908-.62.069-.608.069-.608 1.003.07 1.531 1.032 1.531 1.032.892 1.53 2.341 1.088 2.91.832.092-.647.35-1.088.636-1.338-2.22-.253-4.555-1.113-4.555-4.951 0-1.093.39-1.988 1.031-2.688-.103-.253-.446-1.272.098-2.65 0 0 .84-.27 2.75 1.026A9.564 9.564 0 0112 6.844c.85.004 1.705.115 2.504.337 1.909-1.296 2.747-1.027 2.747-1.027.546 1.378.203 2.398.1 2.651.64.7 1.03 1.595 1.03 2.688 0 3.848-2.338 4.695-4.566 4.943.359.309.678.92.678 1.855 0 1.338-.012 2.419-.012 2.747 0 .268.18.58.688.482A10.001 10.001 0 0022 12c0-5.523-4.477-10-10-10z"
                  clip-rule="evenodd"
                />
              </svg>
            </a>
          </div>
        </div>
      </section>

      <!-- Sección 2: Experiencia Laboral -->
      <section id="experience" class="py-20">
        <h2 class="text-4xl font-bold text-center mb-16">
          Experiencia <span class="text-blue-400">Laboral</span>
        </h2>
        <div class="max-w-3xl mx-auto">
          <div class="relative border-l-2 border-slate-700 pl-10">
            <!-- Punto en la línea de tiempo -->
            <div class="absolute -left-1.5 top-1 w-3 h-3 bg-blue-400 rounded-full"></div>

            <!-- Experiencia 1 -->
            <div class="mb-12">
              <h3 class="text-2xl font-bold text-blue-400 font-mono">Tu Puesto Más Reciente</h3>
              <p class="font-semibold text-gray-400 mb-2">
                Nombre de la Empresa | Mes Año - Presente
              </p>
              <ul class="list-disc list-inside text-gray-400 space-y-2">
                <li>
                  Describe una responsabilidad o un logro clave. Intenta cuantificar tus resultados.
                </li>
                <li>
                  Ejemplo: "Desarrollé y mantuve una aplicación web escalable para más de 10,000
                  usuarios usando React y Node.js".
                </li>
                <li>
                  Otro ejemplo: "Reduje el tiempo de carga de la página en un 30% optimizando las
                  consultas a la base de datos".
                </li>
              </ul>
            </div>

            <!-- Punto en la línea de tiempo -->
            <div class="absolute -left-1.5 top-[calc(50%)] w-3 h-3 bg-blue-400 rounded-full"></div>

            <!-- Experiencia 2 -->
            <div class="mb-12">
              <h3 class="text-2xl font-bold text-blue-400 font-mono">Puesto Anterior</h3>
              <p class="font-semibold text-gray-400 mb-2">Otra Empresa | Mes Año - Mes Año</p>
              <ul class="list-disc list-inside text-gray-400 space-y-2">
                <li>Colaboré en un equipo ágil para diseñar nuevas funcionalidades.</li>
                <li>Resolví bugs críticos y mejoré la estabilidad general de la aplicación.</li>
              </ul>
            </div>
          </div>
        </div>
      </section>

      <!-- Sección 3: Proyectos -->
      <section id="projects" class="py-20">
        <h2 class="text-4xl font-bold text-center mb-12">
          Mis <span class="text-blue-400">Proyectos</span>
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <!-- Proyecto 1 -->
          <div class="card-border-gradient transition-all hover:shadow-2xl hover:scale-105">
            <div class="card-content">
              <h3 class="text-2xl font-bold mb-4 text-blue-400 font-mono">Proyecto Tech 1</h3>
              <p class="text-gray-400 mb-6">
                Una breve descripción de tu proyecto. Explica qué problema resuelve y qué
                tecnologías usaste.
              </p>
              <div class="flex flex-wrap gap-2 mb-6">
                <span class="bg-slate-700 text-blue-300 text-sm font-mono px-3 py-1 rounded-full"
                  >React</span
                >
                <span class="bg-slate-700 text-blue-300 text-sm font-mono px-3 py-1 rounded-full"
                  >Node.js</span
                >
                <span class="bg-slate-700 text-blue-300 text-sm font-mono px-3 py-1 rounded-full"
                  >MongoDB</span
                >
              </div>
              <div class="flex space-x-4">
                <a href="#" class="text-blue-400 hover:text-blue-300 transition-colors">Ver Demo</a>
                <a href="#" class="text-blue-400 hover:text-blue-300 transition-colors"
                  >Ver Código</a
                >
              </div>
            </div>
          </div>

          <!-- Proyecto 2 -->
          <div class="card-border-gradient transition-all hover:shadow-2xl hover:scale-105">
            <div class="card-content">
              <h3 class="text-2xl font-bold mb-4 text-blue-400 font-mono">Proyecto Tech 2</h3>
              <p class="text-gray-400 mb-6">
                Una breve descripción de tu proyecto. Explica qué problema resuelve y qué
                tecnologías usaste.
              </p>
              <div class="flex flex-wrap gap-2 mb-6">
                <span class="bg-slate-700 text-blue-300 text-sm font-mono px-3 py-1 rounded-full"
                  >Python</span
                >
                <span class="bg-slate-700 text-blue-300 text-sm font-mono px-3 py-1 rounded-full"
                  >Flask</span
                >
                <span class="bg-slate-700 text-blue-300 text-sm font-mono px-3 py-1 rounded-full"
                  >SQL</span
                >
              </div>
              <div class="flex space-x-4">
                <a href="#" class="text-blue-400 hover:text-blue-300 transition-colors">Ver Demo</a>
                <a href="#" class="text-blue-400 hover:text-blue-300 transition-colors"
                  >Ver Código</a
                >
              </div>
            </div>
          </div>

          <!-- Proyecto 3 (y más...) -->
          <div class="card-border-gradient transition-all hover:shadow-2xl hover:scale-105">
            <div class="card-content">
              <h3 class="text-2xl font-bold mb-4 text-blue-400 font-mono">Proyecto Tech 3</h3>
              <p class="text-gray-400 mb-6">
                Una breve descripción de tu proyecto. Explica qué problema resuelve y qué
                tecnologías usaste.
              </p>
              <div class="flex flex-wrap gap-2 mb-6">
                <span class="bg-slate-700 text-blue-300 text-sm font-mono px-3 py-1 rounded-full"
                  >HTML5</span
                >
                <span class="bg-slate-700 text-blue-300 text-sm font-mono px-3 py-1 rounded-full"
                  >CSS3</span
                >
                <span class="bg-slate-700 text-blue-300 text-sm font-mono px-3 py-1 rounded-full"
                  >JavaScript</span
                >
              </div>
              <div class="flex space-x-4">
                <a href="#" class="text-blue-400 hover:text-blue-300 transition-colors">Ver Demo</a>
                <a href="#" class="text-blue-400 hover:text-blue-300 transition-colors"
                  >Ver Código</a
                >
              </div>
            </div>
          </div>
        </div>
      </section>

      <!-- Sección 4: Cursos y Certificaciones -->
      <section id="courses" class="py-20">
        <h2 class="text-4xl font-bold text-center mb-12">
          Formación y <span class="text-blue-400">Cursos</span>
        </h2>
        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
          <!-- Curso 1 -->
          <div class="card-border-gradient transition-all hover:shadow-2xl hover:scale-105">
            <div class="card-content">
              <h3 class="text-2xl font-bold mb-4 text-blue-400 font-mono">
                Nombre del Curso/Certificación
              </h3>
              <p class="text-gray-400 mb-2 font-semibold">Plataforma (ej. Platzi, Coursera)</p>
              <p class="text-gray-500 text-sm">Fecha: Ene 2023 - Mar 2023</p>
            </div>
          </div>

          <!-- Curso 2 -->
          <div class="card-border-gradient transition-all hover:shadow-2xl hover:scale-105">
            <div class="card-content">
              <h3 class="text-2xl font-bold mb-4 text-blue-400 font-mono">
                Otro Curso Interesante
              </h3>
              <p class="text-gray-400 mb-2 font-semibold">Plataforma (ej. Udemy)</p>
              <p class="text-gray-500 text-sm">Fecha: Abr 2023</p>
            </div>
          </div>

          <!-- Curso 3 -->
          <div class="card-border-gradient transition-all hover:shadow-2xl hover:scale-105">
            <div class="card-content">
              <h3 class="text-2xl font-bold mb-4 text-blue-400 font-mono">
                Especialización en Backend
              </h3>
              <p class="text-gray-400 mb-2 font-semibold">Institución Educativa</p>
              <p class="text-gray-500 text-sm">Completado: Jun 2023</p>
            </div>
          </div>
        </div>
      </section>
    </main>

    <!-- Footer -->
    <footer class="border-t border-slate-700 mt-20">
      <div class="container mx-auto px-6 py-8 text-center text-gray-500">
        <p>&copy; <span id="year"></span> [Tu Nombre]. Todos los derechos reservados.</p>
        <p class="font-mono text-sm mt-2">
          Diseñado con <span class="text-red-500">&hearts;</span> y código.
        </p>
      </div>
    </footer>
  </body>
</template>

<style scoped>
/* Estilos personalizados para aplicar las fuentes y el tema */
body {
  font-family: 'Inter', sans-serif;
  background-color: #0f172a; /* bg-slate-900 */
  color: #d1d5db; /* text-gray-300 */
}

/* Aplicamos la fuente mono a los elementos con la clase card-tech */
.font-mono {
  font-family: 'Roboto Mono', monospace;
}

/* Efecto de borde con gradiente para las tarjetas */
.card-border-gradient {
  position: relative;
  background: #1e293b; /* bg-slate-800 */
  border-radius: 0.5rem; /* rounded-lg */
  overflow: hidden;
  z-index: 1;
}
.card-border-gradient::before {
  content: '';
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background: conic-gradient(from 180deg at 50% 50%, #2563eb 0deg, #38bdf8 180deg, #2563eb 360deg);
  z-index: -1;
  transform: scale(1.02);
  filter: blur(8px);
  opacity: 0;
  transition: opacity 0.3s ease-in-out;
}
.card-border-gradient:hover::before {
  opacity: 1;
}
/* Contenedor interno para que el contenido no se vea afectado por el borde */
.card-content {
  background: #1e293b; /* bg-slate-800 */
  width: 100%;
  height: 100%;
  padding: 1.5rem; /* p-6 */
}
</style>
