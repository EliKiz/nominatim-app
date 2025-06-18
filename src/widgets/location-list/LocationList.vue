<template>
  <div class="location-list">
    <div v-if="locations.length === 0" class="location-list__empty">
      No locations found
    </div>
    <div v-else class="location-list__grid">
      <LocationCard
        v-for="location in locations"
        :key="location.id"
        v-bind="location"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import LocationCard from '@/entities/location/ui/LocationCard/LocationCard.vue'

interface ILocation {
  id: number
  title: string
  subtitle: string
  type: string
  lat: number
  lon: number
}

defineProps<{
  locations: ILocation[]
}>()
</script>

<style lang="scss" scoped>
.location-list {
  margin-top: 24px;

  &__empty {
    text-align: center;
    color: #64748b;
    font-size: 16px;
    padding: 32px;
  }

  &__grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 16px;
  }
}
</style> 