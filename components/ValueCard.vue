<template>
    <div class="bg-gray-800 rounded-lg p-6 text-center w-64 transition-transform hover:scale-105">
      <i :class="[icon, 'text-5xl text-green-500 mb-4']"></i>
      <h4 class="text-xl font-semibold mb-2">{{ title }}</h4>
      <p class="text-gray-300">{{ description }}</p>
    </div>
</template>

<script setup>
defineProps({
  title: String,
  icon: String,
  description: String
})
</script>