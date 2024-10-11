<template>
    <a :href="url" target="_blank" rel="noopener noreferrer" class="block w-full p-4 mb-4 text-white bg-gray-800 rounded-lg hover:bg-gray-700 transition-colors">
      <div class="flex items-center">
        <i :class="icon" class="text-2xl mr-4 text-green-500"></i>
        <div>
          <h3 class="text-lg font-semibold">{{ title }}</h3>
          <p v-if="description" class="text-sm text-gray-400">{{ description }}</p>
        </div>
      </div>
    </a>
</template>

<script setup>
defineProps({
  title: String,
  url: String,
  icon: String,
  description: String
})
</script>