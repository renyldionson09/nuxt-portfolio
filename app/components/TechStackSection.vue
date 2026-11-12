
<script setup lang="ts">
const techCategories = [
  {
    title: 'Web Technologies',
    description: 'Technologies I use to build websites.',
    items: [
      {
        label: 'HTML5',
        src: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg'
      },
      {
        label: 'CSS3',
        src: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg'
      },
      {
        label: 'JavaScript',
        src: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg'
      }
    ]
  },
  {
    title: 'Tools & Platforms',
    description: 'Tools I use for development and collaboration.',
    items: [
      {
        label: 'GitHub',
        src: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg'
      },
      {
        label: 'VS Code',
        src: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg'
      }
    ]
  }
]
</script>

<template>
  <section id="techstack" class="stack-section">
    <div class="stack-container">

      <!-- Section Header -->
      <div class="stack-header">
        <h2 class="stack-title">
          My <span>Tech Stack</span>
        </h2>

        <p class="stack-description">
          Technologies, tools, and platforms that I use
          to design, develop, and improve digital experiences.
        </p>
      </div>

      <!-- Technology Categories -->
      <div class="stack-categories">

        <article
          v-for="category in techCategories"
          :key="category.title"
          class="stack-category-card"
        >
          <h3 class="stack-category-title">
            {{ category.title }}
          </h3>

          <p class="stack-category-description">
            {{ category.description }}
          </p>

          <div class="stack-items">
            <div
              v-for="item in category.items"
              :key="item.label"
              class="stack-item"
            >
              <img
                :src="item.src"
                :alt="item.label + ' logo'"
                :class="{ 'github-icon': item.label === 'GitHub' }"
                loading="lazy"
              />

              <span class="stack-item-name">
                {{ item.label }}
              </span>

              <span class="badge badge-info badge-outline badge-sm">
                {{ category.title === 'Web Technologies' ? 'Web' : 'Tool' }}
              </span>
            </div>
          </div>
        </article>

      </div>
    </div>
  </section>
</template>

<style scoped>
/* Main Section */
.stack-section {
  min-height: 75vh;
  padding: 100px 20px 90px;
  background: transparent;
}

.stack-container {
  width: 100%;
  max-width: 1100px;
  margin: 0 auto;
}

/* Section Header */
.stack-header {
  width: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  margin-bottom: 48px;
}

.stack-title {
  font-size: clamp(2rem, 4vw, 2.8rem);
  font-weight: 700;
  line-height: 1.3;
  color: #ffffff;
  margin: 0 0 20px;
  text-align: center;
}

.stack-title span {
  color: #22d3ee;
}

.stack-description {
  width: 100%;
  max-width: 650px;
  margin: 0 auto;
  color: #94a3b8;
  font-size: 15px;
  line-height: 1.8;
  text-align: center;
}

/* Category Layout */
.stack-categories {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 24px;
  align-items: stretch;
}

/* Category Cards */
.stack-category-card {
  min-width: 0;
  padding: 35px 28px;
  border: 1px solid #334155;
  border-radius: 20px;
  background: rgba(15, 23, 42, 0.9);
  box-shadow: 0 15px 40px rgba(0, 0, 0, 0.15);
  text-align: center;
  transition: all 0.3s ease;
}

.stack-category-card:hover {
  border-color: rgba(34, 211, 238, 0.5);
  transform: translateY(-5px);
}

.stack-category-title {
  font-size: 22px;
  font-weight: 700;
  color: #22d3ee;
  margin: 0 0 12px;
}

.stack-category-description {
  color: #94a3b8;
  font-size: 14px;
  line-height: 1.7;
  margin: 0 0 32px;
}

/* Technology Items */
.stack-items {
  display: grid;
  grid-template-columns: repeat(3, minmax(0, 1fr));
  gap: 14px;
}

.stack-item {
  min-width: 0;
  min-height: 165px;
  padding: 22px 12px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 14px;
  border: 1px solid #334155;
  border-radius: 14px;
  background: rgba(30, 41, 59, 0.8);
  transition: all 0.3s ease;
}

.stack-item:hover {
  transform: translateY(-6px);
  border-color: #22d3ee;
  background: rgba(34, 211, 238, 0.08);
}

.stack-item img {
  width: 52px;
  height: 52px;
  object-fit: contain;
}

.github-icon {
  filter: brightness(0) invert(1);
}

.stack-item-name {
  color: #e2e8f0;
  font-size: 14px;
  font-weight: 500;
  text-align: center;
}

.stack-item .badge {
  min-height: 1.5rem;
  padding-inline: 0.65rem;
  font-size: 0.75rem;
}

/* Tablet */
@media (max-width: 900px) {
  .stack-categories {
    grid-template-columns: 1fr;
    max-width: 650px;
    margin: 0 auto;
  }
}

/* Mobile */
@media (max-width: 768px) {
  .stack-section {
    padding: 80px 16px 70px;
  }

  .stack-header {
    margin-bottom: 36px;
  }

  .stack-category-card {
    padding: 28px 18px;
  }

  .stack-category-title {
    font-size: 20px;
  }

  .stack-items {
    grid-template-columns: repeat(2, minmax(0, 1fr));
    gap: 12px;
  }

  .stack-item {
    min-height: 150px;
    padding: 18px 10px;
  }

  .stack-item img {
    width: 45px;
    height: 45px;
  }
}
</style>
