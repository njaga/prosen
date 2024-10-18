<template>
    <div class="bg-gray-800 rounded-lg overflow-hidden shadow-lg transition-transform hover:scale-105">
      <div class="p-6">
        <div class="flex items-center mb-4">
          <i :class="[icon, 'text-4xl text-green-500 mr-4']"></i>
          <h3 class="text-2xl font-semibold">{{ title }}</h3>
        </div>
        <p class="text-gray-300 mb-4">{{ description }}</p>
        <ul class="space-y-2">
          <li v-for="feature in features" :key="feature" class="flex items-center">
            <i class="fas fa-check text-green-500 mr-2"></i>
            <span>{{ feature }}</span>
          </li>
        </ul>
      </div>
    </div>
</template>

<script setup>
defineProps({
  title: String,
  description: String,
  icon: String,
  features: Array
})
</script>