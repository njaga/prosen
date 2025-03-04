<template>
  <div>
    <NuxtPage />
  </div>
</template>

<script setup>
useHead({
  titleTemplate: (titleChunk) => {
    return titleChunk ? `${titleChunk} - PROSEN` : 'PROSEN - Solutions de Sécurité Professionnelle au Sénégal';
  },
  meta: [
    { name: 'author', content: 'Cheikh Sadibou NDIAYE' },
    { name: 'theme-color', content: '#111827' },
    { name: 'description', content: 'PROSEN est le leader des solutions de sécurité professionnelle au Sénégal. Surveillance, gardiennage, sécurité électronique et protection rapprochée.' },
    { name: 'keywords', content: 'sécurité, surveillance, gardiennage, Sénégal, protection, PROSEN, sécurité électronique' },
    // Open Graph
    { property: 'og:title', content: 'PROSEN - Solutions de Sécurité Professionnelle au Sénégal' },
    { property: 'og:description', content: 'Leader en solutions de sécurité professionnelle au Sénégal: surveillance, gardiennage, sécurité électronique et protection rapprochée.' },
    { property: 'og:image', content: '/img/prosen-logo.png' },
    { property: 'og:url', content: 'https://prosen.sn' },
    { property: 'og:type', content: 'website' },
    // Twitter Card
    { name: 'twitter:card', content: 'summary_large_image' },
    { name: 'twitter:title', content: 'PROSEN - Solutions de Sécurité Professionnelle au Sénégal' },
    { name: 'twitter:description', content: 'Leader en solutions de sécurité professionnelle au Sénégal: surveillance, gardiennage, sécurité électronique et protection rapprochée.' },
    { name: 'twitter:image', content: '/img/prosen-logo.png' },
  ],
  link: [
    { rel: 'canonical', href: 'https://prosen.sn' }
  ]
})
</script>