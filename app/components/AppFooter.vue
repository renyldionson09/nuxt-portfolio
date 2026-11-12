
<script setup lang="ts">
const footerLinks = [
  { label: 'Home', href: '#home' },
  { label: 'About Me', href: '#about' },
  { label: 'Certifications', href: '#certifications' },
  { label: 'Tech Stack', href: '#techstack' },
  { label: 'Contact', href: '#contact' }
]
</script>

<template>
  <footer class="portfolio-footer">
    <div class="footer-container">

      <div class="footer-content">

        <!-- Branding -->
        <div class="footer-brand">
          <h2 class="footer-logo">
            RENYL DIONSON<span>.</span>
          </h2>

          <p class="footer-description">
            Aspiring UI/UX Designer & Web Developer.
            Passionate about creating meaningful,
            modern, and user-friendly digital experiences.
          </p>
        </div>

        <!-- Quick Links -->
        <div class="footer-navigation">
          <h3 class="footer-heading">Quick Links</h3>

          <nav aria-label="Footer navigation">
            <a
              v-for="link in footerLinks"
              :key="link.href"
              :href="link.href"
              class="footer-link"
            >
              {{ link.label }}
            </a>
          </nav>
        </div>

        <!-- Socials -->
        <div class="footer-social">
          <h3 class="footer-heading">Connect With Me</h3>

          <p class="footer-social-description">
            Let's connect and create something amazing.
          </p>

          <div class="footer-social-links">
            <a
              href="https://github.com/renyldionson09"
              target="_blank"
              rel="noopener noreferrer"
              aria-label="GitHub"
              class="footer-social-button"
            >
              <svg aria-hidden="true" viewBox="0 0 24 24" fill="currentColor">
                <path d="M12 .9a11.1 11.1 0 0 0-3.51 21.63c.56.1.76-.24.76-.54v-2.1c-3.1.67-3.76-1.32-3.76-1.32-.51-1.3-1.24-1.65-1.24-1.65-1.01-.69.08-.68.08-.68 1.12.08 1.71 1.15 1.71 1.15 1 1.7 2.62 1.21 3.26.93.1-.72.39-1.21.71-1.49-2.48-.28-5.09-1.24-5.09-5.53 0-1.22.44-2.21 1.15-2.99-.12-.28-.5-1.42.11-2.95 0 0 .94-.3 3.05 1.14a10.6 10.6 0 0 1 5.55 0c2.11-1.44 3.04-1.14 3.04-1.14.61 1.53.23 2.67.11 2.95.72.78 1.15 1.77 1.15 2.99 0 4.3-2.61 5.25-5.1 5.53.4.35.76 1.03.76 2.08v3.08c0 .3.2.65.77.54A11.1 11.1 0 0 0 12 .9Z" />
              </svg>
            </a>

            <a
              href="https://www.linkedin.com/in/renyl-dionson"
              target="_blank"
              rel="noopener noreferrer"
              aria-label="LinkedIn"
              class="footer-social-button"
            >
              <svg aria-hidden="true" viewBox="0 0 24 24" fill="currentColor">
                <path d="M20.45 2H3.55C2.69 2 2 2.68 2 3.52v16.96c0 .84.69 1.52 1.55 1.52h16.9c.86 0 1.55-.68 1.55-1.52V3.52c0-.84-.69-1.52-1.55-1.52ZM7.93 18.45H4.96V9.02h2.97v9.43ZM6.45 7.73a1.72 1.72 0 1 1 0-3.44 1.72 1.72 0 0 1 0 3.44Zm12 10.72h-2.96v-4.59c0-1.09-.02-2.49-1.52-2.49-1.52 0-1.75 1.19-1.75 2.41v4.67H9.26V9.02h2.84v1.29h.04c.4-.74 1.36-1.52 2.8-1.52 3 0 3.55 1.97 3.55 4.53v5.13Z" />
              </svg>
            </a>
          </div>
        </div>

      </div>

    </div>
  </footer>
</template>

<style scoped>
.portfolio-footer {
  width: 100%;
  background: #090f1e;
  border-top: 1px solid #25334b;
  padding: 65px 20px 25px;
}

.footer-container {
  max-width: 1100px;
  margin: 0 auto;
}

.footer-content {
  display: grid;
  grid-template-columns: 1.5fr 1fr 1fr;
  gap: 60px;
  padding-bottom: 50px;
}

.footer-logo {
  font-size: 36px;
  font-weight: 800;
  color: white;
  margin-bottom: 16px;
}

.footer-logo span {
  color: #22d3ee;
}

.footer-description {
  max-width: 360px;
  font-size: 14px;
  color: #94a3b8;
  line-height: 1.9;
}

.footer-heading {
  font-size: 16px;
  font-weight: 700;
  color: white;
  margin-bottom: 22px;
}

.footer-navigation nav {
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.footer-link {
  color: #94a3b8;
  font-size: 14px;
  text-decoration: none;
  transition: color 0.3s ease;
}

.footer-link:hover {
  color: #22d3ee;
}

.footer-social-description {
  color: #94a3b8;
  font-size: 14px;
  line-height: 1.8;
  margin-bottom: 20px;
}

.footer-social-links {
  display: flex;
  gap: 14px;
}

.footer-social-button {
  width: 44px;
  height: 44px;
  display: flex;
  align-items: center;
  justify-content: center;
  background: #17233c;
  border: 1px solid #334155;
  border-radius: 12px;
  color: #e2e8f0;
  font-size: 20px;
  text-decoration: none;
  transition: all 0.3s ease;
  cursor: pointer;
}

.footer-social-button svg {
  width: 20px;
  height: 20px;
}

.footer-social-button:hover {
  background: #22d3ee;
  color: #090f1e;
  transform: translateY(-4px);
}

@media (max-width: 768px) {
  .portfolio-footer {
    padding: 50px 20px 25px;
  }

  .footer-content {
    grid-template-columns: 1fr;
    gap: 35px;
  }

}
</style>
