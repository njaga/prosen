<template>
    <div class="min-h-screen bg-gray-900 text-white flex flex-col justify-center items-center p-4">
        <div class="max-w-3xl w-full"> <!-- Réduit la largeur maximale -->
            <div class="text-center mb-12">
                <img src="/img/prosen-logo.png" alt="PROSEN Logo" class="w-24 h-24 mx-auto mb-6 rounded-full" />
                <h1 class="text-4xl font-bold mb-2">Cheikh Sadibou NDIAYE</h1>
                <p class="text-xl text-green-500">Directeur Général de PROSEN</p>
            </div>

            <div class="grid grid-cols-1 max-w-4xl content-center md:grid-cols-2 gap-6 mb-12">
                <ContactItem icon="fas fa-phone" title="Mobile" value="+221789649490" />
                <ContactItem icon="fas fa-envelope" title="Email" value="cheikh.ndiaye@prosen.sn" />
            </div>

            <div class="flex justify-center space-x-6 mb-12">
                <SocialIcon icon="fas fa-phone" url="tel:+221789649490" />
                <SocialIcon icon="fas fa-envelope" url="mailto:cheikh.ndiaye@prosen.sn" />
                <SocialIcon icon="fab fa-whatsapp" url="https://wa.me/221789649490" />
                <SocialIcon icon="fas fa-comment" url="sms:+221789649490" />
            </div>

            <LinkItem title="Localisation Bureau"
                url="https://www.google.fr/maps/dir/Voie+de+degagement+N,+Dakar/PJVV%2B38C+Thiaroye+azure,+Dakar/@14.7396441,-17.4555719,13z/data=!3m1!4b1!4m13!4m12!1m5!1m1!1s0xec10d52713a9dfb:0xb55d90857ea25d8f!2m2!1d-17.4726702!2d14.7302386!1m5!1m1!1s0xec10b508783b9f9:0xcdda92dc58dc81e4!2m2!1d-17.355477!2d14.7433008?entry=ttu&g_ep=EgoyMDI0MDkyNS4wIKXMDSoASAFQAw%3D%3D"
                icon="fas fa-map-marker-alt" />
            <LinkItem title="Site Web" url="https://prosen.sn" icon="fas fa-globe"
                description="Cliquer pour visiter notre site web" />
            <LinkItem title="Profil LinkedIn Prosen" url="https://www.linkedin.com/in/prosen-sarl-llc-5b6216111/"
                icon="fab fa-linkedin" description="Cliquer pour suivre notre page sur LinkedIn" />
            <LinkItem title="Calendrier de RDV"
                url="https://calendly.com/thiawjeanclaude/prendre-un-rendez-vous-clone?month=2024-10"
                icon="far fa-calendar-alt" description="Cliquer pour prendre rdv avec Mr NDIAYE" />

            <!-- Section Services mise à jour -->
            <section class="mb-16">
                <h2 class="text-4xl font-bold mb-8 text-center">Nos Services</h2>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                    <ServiceCard 
                        v-for="service in services" 
                        :key="service.title"
                        :title="service.title"
                        :description="service.description"
                        :icon="service.icon"
                        :features="service.features"
                    />
                </div>
            </section>

            <!-- Section Valeurs -->
            <section class="mb-16">
                <h2 class="text-4xl font-bold mb-8 text-center">Nos Valeurs</h2>
                <div class="flex flex-wrap justify-center gap-8">
                    <ValueCard 
                        v-for="value in values" 
                        :key="value.title"
                        :title="value.title"
                        :icon="value.icon"
                        :description="value.description"
                    />
                </div>
            </section>

            <!-- Bouton de téléchargement de la plaquette -->
            <div class="text-center mb-16">
                <a href="/pdf/PLAQUETTE PROSEN.pdf" download class="bg-green-500 text-white py-3 px-6 rounded-full hover:bg-green-600 transition-colors inline-flex items-center">
                    <i class="fas fa-download mr-2"></i>
                    Télécharger notre plaquette
                </a>
            </div>

            <!-- Boutons mis à jour -->
            <div class="fixed bottom-4 left-4 flex space-x-4">
                <button @click="share" class="bg-blue-500 text-white rounded-full p-4 hover:bg-blue-600 transition-colors text-2xl w-16 h-16 flex items-center justify-center">
                    <i class="fas fa-share-alt"></i>
                </button>
                <button @click="openScanModal" class="bg-green-500 text-white rounded-full p-4 hover:bg-green-600 transition-colors text-2xl w-16 h-16 flex items-center justify-center">
                    <i class="fas fa-qrcode"></i>
                </button>
            </div>

            <div class="fixed bottom-4 right-4">
                <button class="bg-green-500 text-white rounded-full p-4 text-2xl w-16 h-16 flex items-center justify-center" @click="addToContacts">
                    <i class="fas fa-user-plus"></i>
                </button>
            </div>

            <!-- Modal pour le scan -->
            <div v-if="showScanModal" class="fixed inset-0 bg-black bg-opacity-50 backdrop-blur-sm flex items-center justify-center z-50">
                <div class="bg-gray-800 p-8 rounded-lg max-w-sm w-full relative">
                    <button @click="closeScanModal" class="absolute top-2 right-2 text-gray-400 hover:text-white">
                        <i class="fas fa-times text-xl"></i>
                    </button>
                    <h3 class="text-2xl font-bold mb-6 text-center">Ajouter votre Carte de Visite Digitale</h3>
                    <button @click="addToGoogleWallet" class="w-full bg-white text-black py-3 rounded-lg mb-4 flex items-center justify-center font-semibold">
                        <img src="/img/google-wallet-logo.png" alt="Google Wallet" class="w-6 h-6 mr-2">
                        Ajouter à Google Wallet
                    </button>
                    <button @click="addToAppleWallet" class="w-full bg-black text-white py-3 rounded-lg flex items-center justify-center font-semibold">
                        <i class="fab fa-apple text-xl mr-2"></i>
                        Ajouter à Apple Wallet
                    </button>
                </div>
            </div>
        </div>
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
        title: "Conseil en Sécurité",
        description: "Expertise pour optimiser votre stratégie de sécurité",
        icon: "fas fa-clipboard-check",
        features: ["Audits de sécurité", "Plans de sécurité", "Formation du personnel"]
    },
    {
        title: "Sécurité Incendie",
        description: "Prévention et intervention rapide en cas d'incendie",
        icon: "fas fa-fire-extinguisher",
        features: ["Systèmes de détection", "Équipements anti-incendie", "Formation aux procédures"]
    },
    {
        title: "Cybersécurité",
        description: "Protection de vos actifs numériques contre les menaces en ligne",
        icon: "fas fa-shield-alt",
        features: ["Pare-feu avancés", "Détection d'intrusion", "Sécurisation des données"]
    }
]

const values = [
    {
        title: "Expertise Inégalée",
        icon: "fas fa-star",
        description: "Notre équipe hautement qualifiée garantit des solutions de sécurité optimales."
    },
    {
        title: "Qualité Certifiée",
        icon: "fas fa-certificate",
        description: "Nos services répondent aux normes les plus strictes de l'industrie."
    },
    {
        title: "Proximité Client",
        icon: "fas fa-handshake",
        description: "Nous travaillons en étroite collaboration avec nos clients pour répondre à leurs besoins spécifiques."
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
    // Logique pour ajouter à Google Wallet
    console.log("Ajout à Google Wallet")
    // Ici, vous devriez implémenter la logique réelle pour ajouter à Google Wallet
    // Par exemple, en utilisant l'API Google Pay Pass
}

const addToAppleWallet = () => {
    // Logique pour ajouter à Apple Wallet
    console.log("Ajout à Apple Wallet")
    // Ici, vous devriez implémenter la logique réelle pour ajouter à Apple Wallet
    // Par exemple, en générant un fichier .pkpass et en l'ouvrant
}

const share = () => {
    if (navigator.share) {
        navigator.share({
            title: 'PROSEN - Votre partenaire en sécurité',
            text: 'Découvrez les services de sécurité professionnels de PROSEN',
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
        // Fallback pour les navigateurs qui ne supportent pas l'API Contacts
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
    background-color: #111827;
    color: white;
    font-family: "Poppins", sans-serif;
}

.backdrop-blur-sm {
    backdrop-filter: blur(4px);
}
</style>