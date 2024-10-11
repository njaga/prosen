<template>
    <a :href="url" target="_blank" rel="noopener noreferrer" class="text-3xl text-green-500 hover:text-green-600 transition-colors">
      <i :class="icon"></i>
    </a>
  </template>
  
  <script setup>
  defineProps({
    icon: {
      type: String,
      required: true
    },
    url: {
      type: String,
      required: true
    }
  })
  </script>