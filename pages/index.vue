<template>
    <div class="min-h-screen bg-gray-900 text-white">
        <!-- Hero Section avec animation -->
        <section class="relative h-screen flex items-center justify-center bg-gradient-to-b from-gray-800 to-gray-900 overflow-hidden">
            <div class="absolute inset-0">
                <div class="absolute inset-0 bg-black opacity-60"></div>
                <div class="absolute inset-0 bg-gradient-to-r from-green-600/30 to-blue-600/30"></div>
            </div>
            <div class="relative z-10 text-center px-4 animate-fadeIn">
                <img src="/img/prosen-logo.png" alt="PROSEN Logo" class="w-32 h-32 mx-auto mb-8 animate-float" />
                <h1 class="text-5xl md:text-7xl font-bold mb-4 animate-slideUp">PROSEN</h1>
                <p class="text-xl md:text-2xl text-green-400 mb-8 animate-slideUp delay-200">Votre Partenaire en Sécurité Professionnelle</p>
                <div class="flex flex-col md:flex-row gap-4 justify-center animate-slideUp delay-300">
                    <a href="#services" class="group bg-green-500 text-white px-8 py-3 rounded-full hover:bg-green-600 transition-all transform hover:scale-105">
                        Nos Services
                        <i class="fas fa-arrow-right ml-2 group-hover:translate-x-1 transition-transform"></i>
                    </a>
                    <a href="/pdf/PLAQUETTE PROSEN.pdf" download class="group bg-transparent border-2 border-white px-8 py-3 rounded-full hover:bg-white hover:text-gray-900 transition-all transform hover:scale-105">
                        Documentation
                        <i class="fas fa-download ml-2 group-hover:translate-y-1 transition-transform"></i>
                    </a>
                </div>
            </div>
            <div class="absolute bottom-10 left-1/2 transform -translate-x-1/2 animate-bounce">
                <a href="#about" class="text-white">
                    <i class="fas fa-chevron-down text-2xl"></i>
                </a>
            </div>
        </section>

        <!-- About Section -->
        <section id="about" class="py-20 px-4">
            <div class="max-w-7xl mx-auto">
                <div class="grid grid-cols-1 md:grid-cols-2 gap-12 items-center">
                    <div class="space-y-6">
                        <h2 class="text-4xl font-bold mb-6">À Propos de PROSEN</h2>
                        <p class="text-gray-300 leading-relaxed">
                            PROSEN est un leader dans le domaine de la sécurité professionnelle au Sénégal. Depuis notre création, nous nous engageons à fournir des solutions de sécurité innovantes et sur mesure pour répondre aux besoins spécifiques de nos clients.
                        </p>
                        <div class="grid grid-cols-2 gap-6 mt-8">
                            <div class="text-center p-4 bg-gray-800 rounded-lg">
                                <div class="text-3xl font-bold text-green-500 mb-2">5+</div>
                                <div class="text-sm text-gray-400">Années d'expérience</div>
                            </div>
                            <div class="text-center p-4 bg-gray-800 rounded-lg">
                                <div class="text-3xl font-bold text-green-500 mb-2">50+</div>
                                <div class="text-sm text-gray-400">Clients satisfaits</div>
                            </div>
                        </div>
                    </div>
                    <div class="relative">
                        <div class="aspect-video bg-gray-800 rounded-lg overflow-hidden">
                            <!-- Remplacer par une vraie image ou vidéo -->
                            <img src="/1x/image prosen.png" alt="PROSEN Logo" class="w-full h-full object-cover">
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Services Section améliorée -->
        <section id="services" class="py-20 px-4 bg-gray-800 relative">
            <div class="absolute inset-0 bg-gradient-to-b from-transparent to-gray-900/50"></div>
            <div class="max-w-7xl mx-auto relative z-10">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold mb-4">Nos Services</h2>
                    <p class="text-gray-400 max-w-2xl mx-auto">
                        Des solutions de sécurité complètes adaptées à vos besoins spécifiques
                    </p>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
                    <ServiceCard 
                        v-for="service in services" 
                        :key="service.title"
                        :title="service.title"
                        :description="service.description"
                        :icon="service.icon"
                        :features="service.features"
                    />
                </div>
            </div>
        </section>

        <!-- Nouvelle section Pourquoi Nous Choisir -->
        <section class="py-20 px-4">
            <div class="max-w-7xl mx-auto">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold mb-4">Pourquoi Nous Choisir</h2>
                    <p class="text-gray-400 max-w-2xl mx-auto">
                        PROSEN se distingue par son expertise et son engagement envers l'excellence
                    </p>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                    <div class="p-6 bg-gray-800 rounded-lg hover:bg-gray-700 transition-colors">
                        <i class="fas fa-certificate text-3xl text-green-500 mb-4"></i>
                        <h3 class="text-xl font-semibold mb-3">Certification ISO</h3>
                        <p class="text-gray-400">Nos processus respectent les normes internationales de qualité</p>
                    </div>
                    <div class="p-6 bg-gray-800 rounded-lg hover:bg-gray-700 transition-colors">
                        <i class="fas fa-users text-3xl text-green-500 mb-4"></i>
                        <h3 class="text-xl font-semibold mb-3">Équipe Qualifiée</h3>
                        <p class="text-gray-400">Personnel hautement formé et régulièrement mis à niveau</p>
                    </div>
                    <div class="p-6 bg-gray-800 rounded-lg hover:bg-gray-700 transition-colors">
                        <i class="fas fa-shield-alt text-3xl text-green-500 mb-4"></i>
                        <h3 class="text-xl font-semibold mb-3">Solutions Sur Mesure</h3>
                        <p class="text-gray-400">Approche personnalisée pour chaque client</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Values Section avec animation -->
        <section class="py-20 px-4 bg-gray-800">
            <div class="max-w-7xl mx-auto">
                <h2 class="text-4xl font-bold mb-12 text-center">Nos Valeurs</h2>
                <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-8">
                    <div v-for="value in values" 
                         :key="value.title" 
                         class="p-6 bg-gray-700 rounded-lg hover:bg-gray-600 transition-all transform hover:-translate-y-1">
                        <div class="flex flex-col items-center sm:items-start">
                            <i :class="[value.icon, 'text-4xl text-green-500 mb-4']"></i>
                            <h3 class="text-xl font-semibold mb-3 text-center sm:text-left">{{ value.title }}</h3>
                            <p class="text-gray-300 text-center sm:text-left">{{ value.description }}</p>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section améliorée -->
        <section class="py-20 px-4">
            <div class="max-w-7xl mx-auto">
                <div class="text-center mb-16">
                    <h2 class="text-4xl font-bold mb-4">Contactez-nous</h2>
                    <p class="text-gray-400 max-w-2xl mx-auto">
                        Notre équipe est à votre disposition pour répondre à toutes vos questions
                    </p>
                </div>
                <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
                    <div class="p-8 bg-gray-800 rounded-lg hover:bg-gray-700 transition-all transform hover:-translate-y-1">
                        <i class="fas fa-map-marker-alt text-4xl text-green-500 mb-6"></i>
                        <h3 class="text-xl font-semibold mb-4">Notre Adresse</h3>
                        <p class="text-gray-400">Immeuble Ellipse, rue 1 X D Pav Usina, Point E, Dakar - Sénégal</p>
                    </div>
                    <div class="p-8 bg-gray-800 rounded-lg hover:bg-gray-700 transition-all transform hover:-translate-y-1">
                        <i class="fas fa-phone text-4xl text-green-500 mb-6"></i>
                        <h3 class="text-xl font-semibold mb-4">Téléphone</h3>
                        <a href="tel:+221338434633" class="text-gray-400 hover:text-green-500 transition-colors">
                            +221 33 843 46 33
                        </a>
                    </div>
                    <div class="p-8 bg-gray-800 rounded-lg hover:bg-gray-700 transition-all transform hover:-translate-y-1">
                        <i class="fas fa-envelope text-4xl text-green-500 mb-6"></i>
                        <h3 class="text-xl font-semibold mb-4">Email</h3>
                        <a href="mailto:contact@prosen.sn" class="text-gray-400 hover:text-green-500 transition-colors">
                            contact@prosen.sn
                        </a>
                    </div>
                </div>
            </div>
        </section>

        <!-- CTA Section améliorée -->
        <section class="py-20 px-4 bg-gradient-to-r from-green-600 to-green-700 relative overflow-hidden">
            <div class="absolute inset-0 bg-pattern opacity-10"></div>
            <div class="max-w-4xl mx-auto text-center relative z-10">
                <h2 class="text-3xl md:text-4xl font-bold mb-6">Prêt à sécuriser votre entreprise ?</h2>
                <p class="text-xl mb-8 text-gray-100">Contactez-nous dès aujourd'hui pour une consultation gratuite</p>
                <a href="mailto:contact@prosen.sn" 
                   class="group bg-white text-gray-900 px-8 py-3 rounded-full hover:bg-gray-100 transition-all transform hover:scale-105 inline-flex items-center">
                    Demander un devis
                    <i class="fas fa-arrow-right ml-2 group-hover:translate-x-1 transition-transform"></i>
                </a>
            </div>
        </section>

        <!-- Footer amélioré -->
        <footer class="py-12 px-4 bg-gray-900">
            <div class="max-w-7xl mx-auto">
                <div class="grid grid-cols-1 md:grid-cols-4 gap-8 mb-8">
                    <div>
                        <img src="/img/prosen-logo.png" alt="PROSEN Logo" class="w-24 h-24 mb-4" />
                        <p class="text-gray-400">Leader en solutions de sécurité professionnelle au Sénégal</p>
                    </div>
                    <div>
                        <h3 class="text-lg font-semibold mb-4">Services</h3>
                        <ul class="space-y-2 text-gray-400">
                            <li><a href="#" class="hover:text-green-500 transition-colors">Surveillance</a></li>
                            <li><a href="#" class="hover:text-green-500 transition-colors">Protection</a></li>
                            <li><a href="#" class="hover:text-green-500 transition-colors">Formation</a></li>
                        </ul>
                    </div>
                    <div>
                        <h3 class="text-lg font-semibold mb-4">Liens Utiles</h3>
                        <ul class="space-y-2 text-gray-400">
                            <li><a href="#" class="hover:text-green-500 transition-colors">À propos</a></li>
                            <li><a href="#" class="hover:text-green-500 transition-colors">Contact</a></li>
                            <li><a href="#" class="hover:text-green-500 transition-colors">Carrières</a></li>
                        </ul>
                    </div>
                    <div>
                        <h3 class="text-lg font-semibold mb-4">Suivez-nous</h3>
                        <div class="flex space-x-4">
                            <a href="https://www.linkedin.com/in/prosen-sarl-llc-5b6216111/" 
                               class="text-gray-400 hover:text-green-500 transition-colors">
                                <i class="fab fa-linkedin text-2xl"></i>
                            </a>
                        </div>
                    </div>
                </div>
                <div class="border-t border-gray-800 pt-8 mt-8">
                    <div class="flex flex-col md:flex-row justify-between items-center">
                        <p class="text-gray-400">&copy; {{ new Date().getFullYear() }} PROSEN. Tous droits réservés.</p>
                        <p class="text-gray-400 mt-4 md:mt-0">
                            Développé par <a href="https://ndiagandiaye.com" target="_blank" class="text-green-500 hover:text-green-400">Ndiaga Ndiaye</a>
                        </p>
                    </div>
                </div>
            </div>
        </footer>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import ContactItem from '../components/ContactItem.vue'
import SocialIcon from '../components/SocialIcon.vue'
import LinkItem from '../components/LinkItem.vue'
import ServiceCard from '../components/ServiceCard.vue'
import ValueCard from '../components/ValueCard.vue'

const services = [
    {
        title: "Surveillance & Gardiennage",
        description: "Votre sécurité assurée 24/7 par des professionnels dévoués",
        icon: "fas fa-user-shield",
        features: ["Agents de sécurité formés", "Patrouilles mobiles", "Maîtres-chiens"]
    },
    {
        title: "Sécurité Électronique",
        description: "La technologie de pointe au service de votre protection",
        icon: "fas fa-video",
        features: ["Vidéosurveillance", "Contrôle d'accès", "Alarmes intrusion"]
    },
    {
        title: "Protection Rapprochée",
        description: "Une protection personnalisée pour votre tranquillité d'esprit",
        icon: "fas fa-user-secret",
        features: ["Gardes du corps", "Escortes VIP", "Sécurité événementielle"]
    },
    {
        title: "Nettoyage Professionnel",
        description: "Services de nettoyage complets pour vos locaux",
        icon: "fas fa-broom",
        features: ["Nettoyage bureaux", "Entretien industriel", "Désinfection"]
    },
    {
        title: "Équipements de Protection",
        description: "Fourniture d'EPI et matériel de sécurité",
        icon: "fas fa-hard-hat",
        features: ["EPI", "Matériel de sécurité", "Équipements incendie"]
    },
    {
        title: "Sécurité Incendie",
        description: "Solutions complètes de protection incendie",
        icon: "fas fa-fire-extinguisher",
        features: ["Détection incendie", "Extincteurs", "Plans d'évacuation"]
    },
    {
        title: "Conseil en Sécurité",
        description: "Expertise pour optimiser votre stratégie de sécurité",
        icon: "fas fa-clipboard-check",
        features: ["Audits de sécurité", "Plans de sécurité", "Formation du personnel"]
    },
    {
        title: "Transport de Valeurs",
        description: "Vos biens précieux acheminés en toute sécurité",
        icon: "fas fa-truck",
        features: ["Convoyage sécurisé", "Véhicules blindés", "Protection optimale"]
    },
    {
        title: "Formations",
        description: "Renforcez les compétences de votre équipe",
        icon: "fas fa-chalkboard-teacher",
        features: ["Formation sécurité", "SST", "Prévention incendie"]
    }
]

const values = [
    {
        title: "Excellence Opérationnelle",
        icon: "fas fa-star",
        description: "Notre expertise et notre professionnalisme garantissent des solutions de sécurité optimales."
    },
    {
        title: "Innovation & Technologie",
        icon: "fas fa-robot",
        description: "Nous intégrons les dernières technologies pour une sécurité moderne et efficace."
    },
    {
        title: "Engagement Client",
        icon: "fas fa-handshake",
        description: "Nous développons des partenariats durables basés sur la confiance et la satisfaction."
    },
    {
        title: "Réactivité 24/7",
        icon: "fas fa-clock",
        description: "Une équipe disponible en permanence pour répondre à vos besoins de sécurité."
    }
]

const showScanModal = ref(false)

const openScanModal = () => {
    showScanModal.value = true
}

const closeScanModal = () => {
    showScanModal.value = false
}

const addToGoogleWallet = () => {
    console.log("Ajout à Google Wallet")
}

const addToAppleWallet = () => {
    console.log("Ajout à Apple Wallet")
}

const share = () => {
    if (navigator.share) {
        navigator.share({
            title: 'PROSEN - Solutions de Sécurité Professionnelle',
            text: 'Découvrez les solutions de sécurité innovantes de PROSEN',
            url: window.location.href,
        })
    } else {
        alert('Le partage n\'est pas supporté sur votre appareil')
    }
}

const addToContacts = async () => {
    if ("contacts" in navigator && "ContactsManager" in window) {
        try {
            const props = ["name", "email", "tel", "address"];
            const opts = { multiple: false };
            const contacts = await navigator.contacts.select(props, opts);

            if (contacts.length > 0) {
                const contact = contacts[0];
                contact.name = ["Cheikh Sadibou NDIAYE"];
                contact.email = ["cheikh.ndiaye@prosen.sn", "contact@prosen.sn"];
                contact.tel = ["+221789649490"];
                contact.address = ["Thiaroye Azur cité sapco 2"];

                await navigator.contacts.update(contact);
                alert("Contact ajouté avec succès !");
            }
        } catch (err) {
            console.error("Erreur lors de l'ajout du contact:", err);
            alert(
                "Impossible d'ajouter le contact. Veuillez vérifier les permissions."
            );
        }
    } else {
        const vcard = `BEGIN:VCARD
VERSION:3.0
FN:Cheikh Sadibou NDIAYE
TITLE:Directeur Général de PROSEN
TEL:+221789649490
EMAIL:cheikh.ndiaye@prosen.sn
EMAIL:contact@prosen.sn
ADR:;;Thiaroye Azur cité sapco 2;;;;
END:VCARD`;

        const blob = new Blob([vcard], { type: "text/vcard" });
        const url = URL.createObjectURL(blob);
        const link = document.createElement("a");
        link.href = url;
        link.download = "cheikh_sadibou_ndiaye.vcf";
        document.body.appendChild(link);
        link.click();
        document.body.removeChild(link);
        URL.revokeObjectURL(url);
    }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap");
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css");

body {
    font-family: "Poppins", sans-serif;
}

html {
    scroll-behavior: smooth;
}

.animate-fadeIn {
    animation: fadeIn 1s ease-out;
}

.animate-slideUp {
    animation: slideUp 0.8s ease-out;
}

.animate-float {
    animation: float 6s ease-in-out infinite;
}

@keyframes fadeIn {
    from { opacity: 0; }
    to { opacity: 1; }
}

@keyframes slideUp {
    from { 
        opacity: 0;
        transform: translateY(20px);
    }
    to {
        opacity: 1;
        transform: translateY(0);
    }
}

@keyframes float {
    0% { transform: translateY(0px); }
    50% { transform: translateY(-10px); }
    100% { transform: translateY(0px); }
}

.bg-pattern {
    background-image: url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.1'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
}

.delay-200 {
    animation-delay: 200ms;
}

.delay-300 {
    animation-delay: 300ms;
}
</style>