
<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue'
import { MapPin } from 'lucide-vue-next'
import type { Map as LeafletMap } from 'leaflet'
import 'leaflet/dist/leaflet.css'

const mapContainer = ref<HTMLElement | null>(null)
let map: LeafletMap | null = null

onMounted(async () => {
  if (!mapContainer.value) return

  const L = await import('leaflet')


  const cavite: [number, number] = [14.2800, 120.8700]

  map = L.map(mapContainer.value, {
    scrollWheelZoom: false
  }).setView(cavite, 10)

  L.tileLayer(
    'https://tile.openstreetmap.org/{z}/{x}/{y}.png',
    {
      attribution:
        '&copy; OpenStreetMap contributors',
      maxZoom: 19
    }
  ).addTo(map)

  L.circleMarker(cavite, {
    radius: 20,
    color: '#22d3ee',
    fillColor: '#22d3ee',
    fillOpacity: 0.8,
    weight: 3
  })
    .addTo(map)
    .bindPopup('General Trias, Cavite, Philippines')
})

onBeforeUnmount(() => {
  map?.remove()
  map = null
})
</script>

<template>
  <section id="location" class="location-section">
    <div class="location-container">

      <div class="location-header">
        <div class="location-badge badge badge-info badge-outline">
          <span class="location-badge-icon">
            <MapPin :size="15" />
          </span>
          <span>My Location</span>
        </div>

        <h2 class="location-title">
          Where I'm <span>Based</span>
        </h2>

        <p class="location-description">
          Based in Cavite, Philippines.
        </p>
      </div>

      <div class="location-card">
        <div ref="mapContainer" class="location-map"></div>

        <div class="location-info">
          <MapPin :size="20" />
          <span>General Trias, Cavite, Philippines</span>
        </div>
      </div>

    </div>
  </section>
</template>

<style scoped>
.location-section {
  padding: 100px 20px 90px;
}

.location-container {
  max-width: 1100px;
  margin: 0 auto;
}

.location-header {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  gap: 22px;
  margin-bottom: 48px;
}

.location-badge {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  padding: 0.7rem 1.2rem;
  border-radius: 999px;
  font-weight: 700;
  letter-spacing: 0.02em;
}

.location-badge-icon {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  width: 2rem;
  height: 2rem;
  border-radius: 50%;
  background: rgba(34, 211, 238, 0.18);
  color: #67e8f9;
}

.location-title {
  font-size: clamp(2rem, 4vw, 2.8rem);
  font-weight: 700;
  color: white;
}

.location-title span {
  color: #22d3ee;
}

.location-description {
  color: #94a3b8;
  font-size: 15px;
  line-height: 1.8;
}

.location-card {
  overflow: hidden;
  border: 1px solid #334155;
  border-radius: 20px;
  background: #0f172a;
}

.location-map {
  width: 100%;
  height: 400px;
  z-index: 0;
}

.location-info {
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 12px;
  padding: 22px;
  color: #22d3ee;
  font-weight: 600;
}

@media (max-width: 768px) {
  .location-section {
    padding: 80px 16px 70px;
  }

  .location-map {
    height: 300px;
  }
}
</style>
