<template>
    <div class="bg-gray-800 p-4 rounded-lg">
      <div class="flex items-center">
        <i :class="icon" class="text-2xl mr-4 text-green-500"></i>
        <div>
          <h3 class="text-lg font-semibold">{{ title }}</h3>
          <p class="text-sm text-gray-400">{{ value }}</p>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  defineProps({
    icon: String,
    title: String,
    value: String
  })
  </script>