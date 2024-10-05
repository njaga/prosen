<template>
    <a :href="url" target="_blank" rel="noopener noreferrer" class="block w-full p-4 mb-4 text-center text-white bg-blue-500 rounded-lg hover:bg-blue-600 transition-colors">
      {{ title }}
    </a>
  </template>
  
  <script setup>
  defineProps({
    title: {
      type: String,
      required: true
    },
    url: {
      type: String,
      required: true
    }
  })
  </script>