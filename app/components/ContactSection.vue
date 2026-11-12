
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

        <div class="reach-actions">
          <a
            href="https://github.com/renyldionson09"
            target="_blank"
            rel="noopener noreferrer"
            class="btn btn-info btn-outline reach-button"
          >
            GitHub
          </a>

          <a
            href="https://www.linkedin.com/in/renyl-dionson"
            target="_blank"
            rel="noopener noreferrer"
            class="btn btn-secondary btn-outline reach-button"
          >
            LinkedIn
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
  min-width: 125px;
  min-height: 44px;
  padding: 10px 24px;
  border-radius: 10px;
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
</style>
