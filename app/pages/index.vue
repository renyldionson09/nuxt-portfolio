<script setup lang="ts">
import { onMounted } from 'vue'

const navLinks = [
  { href: '#home', label: 'Home', active: true },
  { href: '#about', label: 'About Me' },
  { href: '#certifications', label: 'Certifications' },
  { href: '#techstack', label: 'Tech Stacks' },
  { href: '#contact', label: 'Contact' },
]

const certifications = [
  { src: '/Networking_Basic.png', alt: 'Networking Basic Certificate', href: 'https://www.credly.com/badges/84be6d4d-f89f-49f9-9856-ce24e7595746', title: 'NETWORKING BASIC' },
  { src: '/Python_Essentials.png', alt: 'Python Essential 1 Certificate', href: 'https://www.credly.com/badges/3ae2628d-2088-4975-afd2-64bfd514fe93', title: 'PYTHON ESSENTIAL 1' },
  { src: '/software_engineering.png', alt: 'Software Engineering Certificate', href: 'https://learn.saylor.org/admin/tool/certificate/index.php?code=7197250394RD', title: 'SOFTWARE ENGINEERING' },
  { src: '/saylor2.png', alt: 'Introduction to Database Systems Certificate', href: 'https://learn.saylor.org/admin/tool/certificate/index.php?code=1957047708RD', title: 'INTRODUCTION TO DATABASE SYSTEMS' },
  { src: '/C-Cert.png', alt: 'Codechum Certificate', href: 'https://app.codechum.com/certificates/6059', title: 'CODECHUM CERTIFICATE' },
]

const techCategories = [
  {
    title: 'Programming Languages',
    items: [
      { src: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg', label: 'HTML5' },
      { src: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg', label: 'CSS' },
      { src: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg', label: 'JavaScript' },
    ],
  },
  {
    title: 'Tools & Platforms',
    items: [
      { src: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg', label: 'GitHub' },
      { src: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg', label: 'VS Code' },
    ],
  },
]

const openCertificate = (src: string, alt: string) => {
  const modal = document.getElementById('certModal')
  const modalImg = document.getElementById('modalImg')
  const modalCaption = document.getElementById('modalCaption')

  if (modal && modalImg && modalCaption) {
    modal.classList.add('active')
    modalImg.setAttribute('src', src)
    modalImg.setAttribute('alt', alt)
    modalCaption.textContent = alt
    document.body.style.overflow = 'hidden'
  }
}

const closeModal = () => {
  const modal = document.getElementById('certModal')

  if (modal) {
    modal.classList.remove('active')
    document.body.style.overflow = 'auto'
  }
}

onMounted(() => {
  const navToggle = document.querySelector('.nav-toggle')
  const navMenu = document.querySelector('.nav-menu')

  navToggle?.addEventListener('click', () => {
    navToggle.classList.toggle('active')
    navMenu?.classList.toggle('active')
  })

  document.querySelectorAll('.nav-link').forEach((link) => {
    link.addEventListener('click', () => {
      navToggle?.classList.remove('active')
      navMenu?.classList.remove('active')
    })
  })

  const modal = document.getElementById('certModal')
  const modalClose = document.getElementById('modalClose')

  document.querySelectorAll('.cert-image').forEach((img) => {
    img.addEventListener('click', () => {
      const target = img as HTMLImageElement
      openCertificate(target.src, target.alt)
    })
  })

  modalClose?.addEventListener('click', closeModal)

  modal?.addEventListener('click', (event) => {
    if (event.target === modal) {
      closeModal()
    }
  })

  document.addEventListener('keydown', (event) => {
    if (event.key === 'Escape') {
      closeModal()
    }
  })

  document.querySelectorAll('a[href^="#"]').forEach((anchor) => {
    anchor.addEventListener('click', (event) => {
      const targetSelector = (anchor as HTMLAnchorElement).getAttribute('href')
      const target = targetSelector ? document.querySelector(targetSelector) : null
      if (!target) {
        return
      }

      event.preventDefault()
      target.scrollIntoView({ behavior: 'smooth', block: 'start' })
    })
  })

  window.addEventListener('scroll', () => {
    const navbar = document.querySelector('.navbar')
    if (navbar) {
      navbar.setAttribute(
        'style',
        window.scrollY > 50
          ? 'background: rgba(26, 26, 46, 0.98);'
          : 'background: rgba(26, 26, 46, 0.95);',
      )
    }
  })
})

useHead({
  title: 'Renyl Dionson | Portfolio',
  meta: [{ name: 'description', content: 'Portfolio of Renyl Dionson, aspiring UI/UX designer and IT student.' }],
})
</script>

<template>
  <div>
    <nav class="navbar">
      <div class="nav-container">
        <a href="#home" class="logo">RD</a>
        <button class="nav-toggle" aria-label="Toggle navigation">
          <span class="hamburger" />
        </button>
        <ul class="nav-menu">
          <li v-for="link in navLinks" :key="link.href">
            <a :href="link.href" :class="['nav-link', { active: link.active }]">{{ link.label }}</a>
          </li>
        </ul>
      </div>
    </nav>

    <main>
      <section id="home" class="hero">
        <div class="hero-content">
          <div class="profile-image">
            <img src="/image3.jpg" alt="Renyl Dionson - Professional Portrait" />
          </div>
          <h1 class="hero-title">Hi! I'm <span class="highlight">Renyl Dionson</span></h1>
          <p class="hero-subtitle">Aspiring UI/UX Designer</p>
        </div>
      </section>

      <section id="about" class="about-section">
        <div class="container">
          <h1 class="section-title">About <span class="highlight">Me</span></h1>

          <div class="about-content">
            <div class="about-image">
              <img src="/image3.jpg" alt="Renyl Dionson" />
            </div>

            <div class="about-text">
              <p class="about-paragraph">
                As an aspiring UI/UX Designer and IT student, I specialize in crafting user-centered digital experiences
                that balance aesthetic appeal with seamless functionality. I am passionate about solving complex user
                problems through intuitive design and am constantly refining my skills in wireframing, prototyping, and
                visual storytelling.
              </p>

              <p class="about-paragraph">
                My goal is to design innovative interfaces that simplify lives while setting new industry standards for
                usability and inclusive design. I thrive on continuous growth and look forward to leading creative teams
                in building impactful, design-driven products.
              </p>
            </div>
          </div>
        </div>
      </section>

      <section id="certifications" class="certifications-section">
        <div class="container">
          <h1 class="section-title">My <span class="highlight">Certifications</span></h1>

          <div class="certifications-grid">
            <div v-for="certificate in certifications" :key="certificate.title" class="certification-card">
              <img
                :src="certificate.src"
                :alt="certificate.alt"
                class="cert-image"
                @click="openCertificate(certificate.src, certificate.alt)"
              />
              <h3 class="cert-title">
                <a :href="certificate.href" target="_blank" rel="noopener noreferrer">{{ certificate.title }}</a>
              </h3>
            </div>
          </div>
        </div>
      </section>

      <div class="modal" id="certModal">
        <span class="modal-close" id="modalClose">&times;</span>
        <img class="modal-content" id="modalImg" src="" alt="" />
        <div class="modal-caption" id="modalCaption" />
      </div>

      <section id="techstack" class="techstack-section">
        <div class="container">
          <h1 class="section-title">My <span class="highlight">Tech Stack</span></h1>

          <div class="tech-categories">
            <div v-for="category in techCategories" :key="category.title" class="tech-category">
              <h2 class="category-title">{{ category.title }}</h2>

              <div class="tech-grid">
                <div v-for="item in category.items" :key="item.label" class="tech-item">
                  <img :src="item.src" :alt="item.label" />
                  <span>{{ item.label }}</span>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      <section id="contact" class="contact-section">
        <div class="container">
          <h1 class="section-title">Get In <span class="highlight">Touch</span></h1>

          <div class="contact-content">
            <div class="contact-info">
              <h2>Let's Connect</h2>
              <p>
                Feel free to reach out through any of the platforms below. I'm always open to discussing new projects,
                creative ideas, or opportunities to be part of your vision.
              </p>

              <div class="contact-links">
                <a href="https://www.linkedin.com/in/renyl-dionson" target="_blank" rel="noopener noreferrer" class="contact-link linkedin">
                  <i class="fab fa-linkedin" />
                  <span>LinkedIn</span>
                </a>
                <a href="https://github.com/renyldionson09" target="_blank" rel="noopener noreferrer" class="contact-link github">
                  <i class="fab fa-github" />
                  <span>GitHub</span>
                </a>
              </div>
            </div>
          </div>
        </div>
      </section>
    </main>
  </div>
</template>
