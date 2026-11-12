
<script setup lang="ts">
import { ref } from 'vue'

const isMenuOpen = ref(false)

const navLinks = [
  { href: '#home', label: 'Home' },
  { href: '#about', label: 'About Me' },
  { href: '#certifications', label: 'Certifications' },
  { href: '#techstack', label: 'Tech Stacks' },
  { href: '#contact', label: 'Contact' }
]

const closeMenu = () => {
  isMenuOpen.value = false
}
</script>

<template>
  <nav class="navbar">
    <div class="nav-container">

      <a href="#home" class="logo" @click="closeMenu">
        RD
      </a>

      <button
        class="nav-toggle"
        :class="{ active: isMenuOpen }"
        type="button"
        aria-label="Toggle navigation"
        :aria-expanded="isMenuOpen"
        aria-controls="portfolio-nav"
        @click="isMenuOpen = !isMenuOpen"
      >
        <span class="hamburger"></span>
      </button>

      <ul
        id="portfolio-nav"
        class="nav-menu"
        :class="{ active: isMenuOpen }"
      >
        <li v-for="link in navLinks" :key="link.href">
          <a
            :href="link.href"
            class="nav-link"
            :class="{ active: link.href === '#home' }"
            @click="closeMenu"
          >
            {{ link.label }}
          </a>
        </li>
      </ul>

    </div>
  </nav>
</template>
