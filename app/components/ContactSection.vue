
<template>
  <section id="contact" class="reach-section">
    <div class="reach-container">

      <!-- Section Header -->
      <div class="reach-header">
        <h2 class="reach-title">
          Get In <span>Touch</span>
        </h2>

        <p class="reach-description">
          Have a project in mind or want to collaborate?
          Feel free to connect with me.
        </p>
      </div>

      <!-- Contact Card -->
      <div class="reach-card">

        <div class="badge badge-info badge-outline reach-badge">
          Let's Connect
        </div>

        <h3 class="reach-card-title">
          Let's Work Together!
        </h3>

        <p class="reach-card-description">
          Whether it's web development, UI/UX design,
          or something creative, I'd love to hear from you.
          Let's turn great ideas into meaningful
          digital experiences.

          
        </p>

        <!-- Social Links -->
        <div class="reach-actions">
          <a
            href="https://github.com/renyldionson09"
            target="_blank"
            rel="noopener noreferrer"
            class="btn btn-info btn-outline reach-button"
          >
            <svg aria-hidden="true" viewBox="0 0 24 24" fill="currentColor">
              <path d="M12 .9a11.1 11.1 0 0 0-3.51 21.63c.56.1.76-.24.76-.54v-2.1c-3.1.67-3.76-1.32-3.76-1.32-.51-1.3-1.24-1.65-1.24-1.65-1.01-.69.08-.68.08-.68 1.12.08 1.71 1.15 1.71 1.15 1 1.7 2.62 1.21 3.26.93.1-.72.39-1.21.71-1.49-2.48-.28-5.09-1.24-5.09-5.53 0-1.22.44-2.21 1.15-2.99-.12-.28-.5-1.42.11-2.95 0 0 .94-.3 3.05 1.14a10.6 10.6 0 0 1 5.55 0c2.11-1.44 3.04-1.14 3.04-1.14.61 1.53.23 2.67.11 2.95.72.78 1.15 1.77 1.15 2.99 0 4.3-2.61 5.25-5.1 5.53.4.35.76 1.03.76 2.08v3.08c0 .3.2.65.77.54A11.1 11.1 0 0 0 12 .9Z" />
            </svg>
            <span>GitHub</span>s
          </a>

          <a
            href="https://www.linkedin.com/in/renyl-dionson-97b927409"
            target="_blank"
            rel="noopener noreferrer"
            class="btn btn-secondary btn-outline reach-button"
          >
            <svg aria-hidden="true" viewBox="0 0 24 24" fill="currentColor">
              <path d="M20.45 2H3.55C2.69 2 2 2.68 2 3.52v16.96c0 .84.69 1.52 1.55 1.52h16.9c.86 0 1.55-.68 1.55-1.52V3.52c0-.84-.69-1.52-1.55-1.52ZM7.93 18.45H4.96V9.02h2.97v9.43ZM6.45 7.73a1.72 1.72 0 1 1 0-3.44 1.72 1.72 0 0 1 0 3.44Zm12 10.72h-2.96v-4.59c0-1.09-.02-2.49-1.52-2.49-1.52 0-1.75 1.19-1.75 2.41v4.67H9.26V9.02h2.84v1.29h.04c.4-.74 1.36-1.52 2.8-1.52 3 0 3.55 1.97 3.55 4.53v5.13Z" />
            </svg>
            <span>LinkedIn</span>
          </a>
        </div>

      </div>
    </div>
  </section>
</template>


<style scoped>
.reach-section {
  min-height: 75vh;
  padding: 100px 20px 90px;
  background: transparent;
}

.reach-container {
  width: 100%;
  max-width: 1100px;
  margin: 0 auto;
}

/* Header */
.reach-header {
  text-align: center;
  margin-bottom: 36px;
}

.reach-title {
  font-size: clamp(2rem, 4vw, 2.8rem);
  font-weight: 700;
  line-height: 1.3;
  color: #ffffff;
  margin: 0 0 20px;
}

.reach-title span {
  color: #22d3ee;
}

.reach-description {
  max-width: 650px;
  margin: 0 auto;
  color: #94a3b8;
  font-size: 15px;
  line-height: 1.8;
  text-align: center;
}

/* Contact Card */
.reach-card {
  width: 100%;
  max-width: 780px;
  margin: 0 auto;
  padding: 48px 35px;
  border: 1px solid #334155;
  border-radius: 20px;
  background: rgba(15, 23, 42, 0.9);
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);

  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
}

.reach-card-title {
  font-size: clamp(1.5rem, 3vw, 2rem);
  font-weight: 700;
  color: white;
  margin: 0 0 16px;
}

.reach-badge {
  min-height: 2.5rem;
  margin-bottom: 24px;
  padding: 0 1.25rem;
  font-size: 1rem;
}

.reach-card-description {
  max-width: 560px;
  color: #94a3b8;
  font-size: 15px;
  line-height: 1.8;
  margin: 0 0 32px;
}

.reach-actions {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  gap: 16px;
}


.reach-button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 10px;

  min-width: 150px;
  min-height: 46px;
  padding: 10px 24px;

  border: 1px solid #22d3ee;
  border-radius: 10px;
  background: transparent;
  color: #22d3ee;

  font-size: 14px;
  font-weight: 600;
  text-decoration: none;
  transition: all 0.3s ease;
}

.reach-button:hover {
  background: #22d3ee;
  color: #080f20;
  transform: translateY(-3px);
}

.reach-button svg {
  width: 19px;
  height: 19px;
  flex-shrink: 0;
}


/* Mobile */
@media (max-width: 768px) {
  .reach-section {
    padding: 80px 16px 70px;
  }

  .reach-header {
    margin-bottom: 28px;
  }

  .reach-card {
    padding: 35px 20px;
  }

  .reach-actions {
    gap: 12px;
  }
}

.reach-button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
}
</style>
