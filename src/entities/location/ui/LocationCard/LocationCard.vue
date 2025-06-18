<template>
  <div class="location-card">
    <h3 class="location-card__title">{{ title }}</h3>
    <p class="location-card__subtitle">{{ subtitle }}</p>
    <div class="location-card__details">
      <span class="location-card__type">{{ type }}</span>
      <span class="location-card__coordinates">
        {{ lat }}, {{ lon }}
      </span>
    </div>
  </div>
</template>

<script setup lang="ts">
interface ILocationCardProps {
  title: string
  subtitle: string
  type: string
  lat: number
  lon: number
}

defineProps<ILocationCardProps>()
</script>

<style lang="scss" scoped>
.location-card {
  padding: 16px;
  border: 1px solid #e2e8f0;
  border-radius: 8px;
  background-color: white;
  transition: transform 0.2s ease, box-shadow 0.2s ease;

  &:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 6px -1px rgb(0 0 0 / 0.1);
  }

  &__title {
    font-size: 18px;
    font-weight: 600;
    color: #1e293b;
    margin: 0 0 8px;
  }

  &__subtitle {
    font-size: 14px;
    color: #64748b;
    margin: 0 0 12px;
  }

  &__details {
    display: flex;
    justify-content: space-between;
    align-items: center;
    font-size: 12px;
  }

  &__type {
    color: #3b82f6;
    font-weight: 500;
  }

  &__coordinates {
    color: #64748b;
  }
}
</style> 