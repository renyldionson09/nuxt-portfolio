
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
              <i class="fab fa-github"></i>
            </a>

            <a
              href="https://www.linkedin.com/in/renyl-dionson"
              target="_blank"
              rel="noopener noreferrer"
              aria-label="LinkedIn"
              class="footer-social-button"
            >
              <i class="fab fa-linkedin-in"></i>
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
