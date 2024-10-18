<template>
  <div>
    <NuxtPage />
  </div>
</template>

<script setup>
useHead({
  titleTemplate: (titleChunk) => {
    return titleChunk ? `${titleChunk} - PROSEN` : 'PROSEN - Cheikh Sadibou NDIAYE';
  },
  meta: [
    { name: 'author', content: 'Cheikh Sadibou NDIAYE' },
    { name: 'theme-color', content: '#111827' }, // Couleur de thème pour les navigateurs mobiles
  ],
})
</script>