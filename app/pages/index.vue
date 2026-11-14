
<script setup lang="ts">
import AppNavbar from '../components/AppNavBar.vue'
import HeroSection from '../components/HeroSection.vue'
import AboutSection from '../components/AboutSection.vue'
import CertificationsSection from '../components/CertificationsSection.vue'
import TechStackSection from '../components/TechStackSection.vue'
import LocationSection from '../components/LocationSection.client.vue'
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
</script>

<template>
  <div>
    <AppNavbar />

    <main>

    <HeroSection />

     <AboutSection />

      <CertificationsSection />

      <TechStackSection />

<ClientOnly fallback-tag="div" fallback="Loading location map...">
  <LocationSection />
</ClientOnly>

      <ContactSection />

    </main>
    <AppFooter />
  </div>
</template>
