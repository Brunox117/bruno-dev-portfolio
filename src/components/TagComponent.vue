<template>
  <span
    class="inline-flex items-center px-3 py-1 rounded-full text-sm font-medium bg-blue-400/10 text-blue-400 border border-blue-400/20 hover:bg-blue-400/20 transition-colors duration-200"
  >
    {{ name }}
  </span>
</template>

<script setup lang="ts">
defineProps({
  name: {
    type: String,
    required: true,
  },
});
</script>
