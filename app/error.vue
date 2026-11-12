
<script setup lang="ts">
import type { NuxtError } from '#app'

const props = defineProps<{
  error: NuxtError
}>()

const isNotFound = computed(
  () => props.error.status === 404
)

const goHome = () => {
  clearError({ redirect: '/' })
}

useSeoMeta({
  title: () => isNotFound.value
    ? '404 | Page Not Found'
    : 'Something Went Wrong',
  robots: 'noindex'
})
</script>

<template>
  <main class="error-page">
    <div class="error-card">

      <div class="badge badge-info badge-outline mb-6">
        {{ isNotFound ? 'PAGE NOT FOUND' : 'ERROR' }}
      </div>

      <h1 class="error-number">
        {{ error.status }}
      </h1>

      <h2 class="error-title">
        {{ isNotFound ? 'Oops! Page Not Found' : 'Something Went Wrong' }}
      </h2>

      <p class="error-description">
        {{
          isNotFound
            ? "The page you're looking for doesn't exist or may have been moved."
            : "An unexpected error occurred. Please try returning to the homepage."
        }}
      </p>

      <button
        class="btn btn-info error-button"
        type="button"
        @click="goHome"
      >
        Back to Homepage
      </button>

      <p class="error-footer">
        © {{ new Date().getFullYear() }} Renyl Dionson
      </p>

    </div>
  </main>
</template>

<style scoped>
.error-page {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 40px 20px;
  background: radial-gradient(
    ellipse at center,
    #162445 0%,
    #080f20 70%
  );
  color: white;
  font-family: 'Poppins', sans-serif;
}

.error-card {
  width: 100%;
  max-width: 650px;
  text-align: center;
  padding: 55px 30px;
  border: 1px solid #334155;
  border-radius: 24px;
  background: rgba(15, 23, 42, 0.85);
}

.error-number {
  font-size: clamp(7rem, 20vw, 12rem);
  font-weight: 800;
  line-height: 1.1;
  margin: 0 0 20px;
  background: linear-gradient(
    135deg,
    #22d3ee,
    #a78bfa
  );
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.error-title {
  font-size: clamp(1.5rem, 4vw, 2.3rem);
  font-weight: 700;
  margin-bottom: 20px;
}

.error-description {
  max-width: 450px;
  margin: 0 auto 35px;
  color: #94a3b8;
  line-height: 1.8;
}

.error-button {
  border-radius: 12px;
  padding: 12px 30px;
}

.error-footer {
  margin-top: 50px;
  color: #64748b;
  font-size: 12px;
}
</style>
