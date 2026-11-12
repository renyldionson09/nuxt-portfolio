
<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue'

type Certificate = {
  src: string
  alt: string
  title: string
  href: string
}

const certifications: Certificate[] = [
  {
    src: '/Networking_Basic.png',
    alt: 'Networking Basic Certificate',
    title: 'NETWORKING BASIC',
    href: 'https://www.credly.com/badges/84be6d4d-f89f-49f9-9856-ce24e7595746'
  },
  {
    src: '/Python_Essentials.png',
    alt: 'Python Essential 1 Certificate',
    title: 'PYTHON ESSENTIAL 1',
    href: 'https://www.credly.com/badges/3ae2628d-2088-4975-afd2-64bfd514fe93'
  },
  {
    src: '/software_engineering.png',
    alt: 'Software Engineering Certificate',
    title: 'SOFTWARE ENGINEERING',
    href: 'https://learn.saylor.org/admin/tool/certificate/index.php?code=7197250394RD'
  },
  {
    src: '/saylor2.png',
    alt: 'Introduction to Database Systems Certificate',
    title: 'INTRODUCTION TO DATABASE SYSTEMS',
    href: 'https://learn.saylor.org/admin/tool/certificate/index.php?code=1957047708RD'
  },
  {
    src: '/C-Cert.png',
    alt: 'Codechum Certificate',
    title: 'CODECHUM CERTIFICATE',
    href: 'https://app.codechum.com/certificates/6059'
  }
]

const selectedCertificate = ref<Certificate | null>(null)

const openPreview = (certificate: Certificate) => {
  selectedCertificate.value = certificate
}

const closePreview = () => {
  selectedCertificate.value = null
}

const handleKeydown = (event: KeyboardEvent) => {
  if (event.key === 'Escape') closePreview()
}

onMounted(() => {
  window.addEventListener('keydown', handleKeydown)
})

onBeforeUnmount(() => {
  window.removeEventListener('keydown', handleKeydown)
})
</script>

<template>
  <section id="certifications" class="certifications-section">
    <div class="container">


<div class="w-full flex flex-col items-center text-center !mb-16">

  <h2 class="section-title !mb-8 !text-center !w-full">
    My <span class="highlight">Certifications</span>
  </h2>

  <p class="!text-center text-slate-400 leading-relaxed max-w-2xl mx-auto px-4">
    Certifications and achievements from my
    continuous learning journey in Information Technology.
  </p>

</div>



      <div class="certifications-grid">

        <article
          v-for="certificate in certifications"
          :key="certificate.title"
          class="certification-card card border border-slate-700"
        >
          <button
            type="button"
            class="w-full cursor-pointer"
            :aria-label="'Preview ' + certificate.title"
            @click="openPreview(certificate)"
          >
            <img
              :src="certificate.src"
              :alt="certificate.alt"
              class="cert-image"
              loading="lazy"
            />
          </button>

          <h3 class="cert-title text-center">
            {{ certificate.title }}
          </h3>

          <div class="flex justify-center mt-4">
            <a
              :href="certificate.href"
              target="_blank"
              rel="noopener noreferrer"
              class="btn btn-info btn-outline btn-sm"
            >
              View Credential
            </a>
          </div>
        </article>

      </div>

    </div>

    <!-- Certificate Preview -->
    <div
      v-if="selectedCertificate"
      class="fixed inset-0 z-[9999] flex items-center justify-center bg-black/90 p-5"
      role="dialog"
      aria-modal="true"
      :aria-label="selectedCertificate.alt"
      @click.self="closePreview"
    >
      <div class="relative w-full max-w-4xl text-center">
        <button
          type="button"
          class="btn btn-circle btn-error absolute right-0 top-0 z-10"
          aria-label="Close preview"
          @click="closePreview"
        >
          ✕
        </button>

        <img
          :src="selectedCertificate.src"
          :alt="selectedCertificate.alt"
          class="mx-auto max-h-[75vh] w-auto max-w-full rounded-xl object-contain"
        />

        <p class="mt-5 text-lg font-semibold text-white">
          {{ selectedCertificate.title }}
        </p>
      </div>
    </div>

  </section>
</template>
