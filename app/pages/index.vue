
<script setup lang="ts">
import { onMounted } from 'vue'
import AppNavbar from '../components/AppNavBar.vue'
import HeroSection from '../components/HeroSection.vue'
import AboutSection from '../components/AboutSection.vue'
import CertificationsSection from '../components/CertificationsSection.vue'
import TechStackSection from '../components/TechStackSection.vue'
import ContactSection from '../components/ContactSection.vue'
import AppFooter from '../components/AppFooter.vue'


useSeoMeta({
  title: 'Renyl Dionson | UI/UX Designer & Web Developer',
  description: 'Personal portfolio of Renyl Dionson, an aspiring UI/UX Designer and Web Developer.',

  ogTitle: 'Renyl Dionson | Portfolio',
  ogDescription: 'Explore my certifications, skills, and journey in UI/UX design and web development.',
  ogType: 'website',

  twitterCard: 'summary'
})

useHead({
  htmlAttrs: {
    lang: 'en'
  },
  meta: [
    {
      name: 'author',
      content: 'Renyl Dionson'
    },
    {
      name: 'theme-color',
      content: '#080f20'
    }
  ]
})



type Certificate = {
  src: string
  alt: string
  href: string
  title: string
}

const certifications: Certificate[] = [
  {
    src: '/Networking_Basic.png',
    alt: 'Networking Basic Certificate',
    href: 'https://www.credly.com/badges/84be6d4d-f89f-49f9-9856-ce24e7595746',
    title: 'NETWORKING BASIC',
  },
  {
    src: '/Python_Essentials.png',
    alt: 'Python Essential 1 Certificate',
    href: 'https://www.credly.com/badges/3ae2628d-2088-4975-afd2-64bfd514fe93',
    title: 'PYTHON ESSENTIAL 1',
  },
  {
    src: '/software_engineering.png',
    alt: 'Software Engineering Certificate',
    href: 'https://learn.saylor.org/admin/tool/certificate/index.php?code=7197250394RD',
    title: 'SOFTWARE ENGINEERING',
  },
  {
    src: '/saylor2.png',
    alt: 'Introduction to Database Systems Certificate',
    href: 'https://learn.saylor.org/admin/tool/certificate/index.php?code=1957047708RD',
    title: 'INTRODUCTION TO DATABASE SYSTEMS',
  },
  {
    src: '/C-Cert.png',
    alt: 'Codechum Certificate',
    href: 'https://app.codechum.com/certificates/6059',
    title: 'CODECHUM CERTIFICATE',
  },
]


const selectedCertificate = ref<{ src: string; alt: string } | null>(null)

function openCertificate(src: string, alt: string) {
  selectedCertificate.value = { src, alt }
  document.body.style.overflow = 'hidden'
}

function closeModal() {
  selectedCertificate.value = null
  document.body.style.overflow = ''
}

function handleKeydown(event: KeyboardEvent) {
  if (event.key === 'Escape' && selectedCertificate.value) closeModal()
}

onMounted(() => document.addEventListener('keydown', handleKeydown))
onBeforeUnmount(() => {
  document.removeEventListener('keydown', handleKeydown)
  document.body.style.overflow = ''
})

</script>

<template>
  <div>
    <AppNavbar />

    <main>

    <HeroSection />

     <AboutSection />

      <CertificationsSection />

      <TechStackSection />

      <ContactSection />

    </main>
    <AppFooter />
  </div>
</template>
