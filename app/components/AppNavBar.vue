
<script setup lang="ts">
import { ref } from 'vue'
import {
  House,
  UserRound,
  Award,
  Code2,
  Mail,
  Menu,
  X
} from 'lucide-vue-next'

const isMenuOpen = ref(false)

const navLinks = [
  { href: '#home', label: 'Home', icon: House },
  { href: '#about', label: 'About Me', icon: UserRound },
  { href: '#certifications', label: 'Certifications', icon: Award },
  { href: '#techstack', label: 'Tech Stacks', icon: Code2 },
  { href: '#contact', label: 'Contact', icon: Mail }
]

const closeMenu = () => {
  isMenuOpen.value = false
}
</script>

<template>
  <nav class="navbar">
    <div class="nav-container">

      <a href="#home" class="logo" @click="closeMenu">
        RD<span class="logo-dot">.</span>
      </a>

      <button
        type="button"
        class="nav-toggle"
        :aria-expanded="isMenuOpen"
        aria-controls="portfolio-nav"
        aria-label="Toggle navigation"
        @click="isMenuOpen = !isMenuOpen"
      >
        <X v-if="isMenuOpen" :size="25" />
        <Menu v-else :size="25" />
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
            @click="closeMenu"
          >
            <component :is="link.icon" :size="18" />
            <span>{{ link.label }}</span>
          </a>
        </li>
      </ul>

    </div>
  </nav>
</template>

<style scoped>
.nav-link {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 9px;
}

.nav-link svg {
  flex-shrink: 0;
}

.nav-toggle {
  color: #22d3ee;
}

.logo-dot {
  color: #a78bfa;
}

@media (max-width: 768px) {
  .nav-link {
    width: 100%;
    padding: 12px 16px;
  }
}
</style>
