<template>
    <div
        class="min-h-screen bg-gradient-to-br from-gray-900 to-black text-white flex flex-col justify-center items-center p-8">
        <div class="max-w-3xl w-full">
            <div v-motion :initial="{ opacity: 0, y: 50 }" :enter="{ opacity: 1, y: 0 }" class="text-center mb-12">
                <img src="/img/ndiaga.ico" alt="Ndiaga Ndiaye Logo" class="w-24 h-24 mx-auto mb-6 rounded-full">
                <h1 class="text-5xl font-bold mb-4">Ndiaga Ndiaye</h1>
                <p class="text-xl text-gray-400">Développeur Web Full Stack</p>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-12">
                <div v-for="(info, key) in contactInfo" :key="key" v-motion :initial="{ opacity: 0, x: -50 }"
                    :enter="{ opacity: 1, x: 0 }"
                    class="bg-white bg-opacity-5 p-4 rounded-lg hover:bg-opacity-10 transition-all duration-300">
                    <div class="flex items-center">
                        <i :class="info.icon" class="text-2xl mr-4 text-blue-500"></i>
                        <div>
                            <h3 class="text-lg font-semibold">{{ info.title }}</h3>
                            <p class="text-sm text-gray-400">{{ info.value }}</p>
                        </div>
                    </div>
                </div>
            </div>

            <div class="flex justify-center space-x-6">
                <a v-for="(link, key) in socialLinks" :key="key" :href="link.url" target="_blank"
                    rel="noopener noreferrer" v-motion :initial="{ opacity: 0, scale: 0.5 }"
                    :enter="{ opacity: 1, scale: 1, transition: { delay: 100 * link.index } }"
                    class="text-3xl text-white hover:text-blue-500 transition-colors duration-300">
                    <i :class="link.icon"></i>
                </a>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const contactInfo = ref({
    email: { title: 'Email', value: 'contact@ndiagandiaye.com', icon: 'fas fa-envelope' },
    phone: { title: 'Téléphone', value: '+221 78 163 34 19', icon: 'fas fa-phone' },
    address: { title: 'Adresse', value: 'Scat Urbam, Dakar, Sénégal - 11500', icon: 'fas fa-map-marker-alt' },
    website: { title: 'Site Web', value: 'ndiagandiaye.com', icon: 'fas fa-globe', url: 'https://ndiagandiaye.com/' },
})

const socialLinks = ref([
    { url: 'https://github.com/njaga', icon: 'fab fa-github', index: 0 },
    { url: 'https://www.facebook.com/njaganjaay', icon: 'fab fa-facebook', index: 1 },
    { url: 'https://www.linkedin.com/in/ndiagandiaye', icon: 'fab fa-linkedin', index: 2 },
    { url: 'https://www.instagram.com/ndiagandiaye01/', icon: 'fab fa-instagram', index: 3 },
    { url: 'https://x.com/ndiaga_dev', icon: 'fab fa-twitter', index: 4 },
])
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap');
@import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css');

body {
    background-color: #111827;
    color: white;
    font-family: 'Poppins', sans-serif;
}
</style>