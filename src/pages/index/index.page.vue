<template>
  <div class="page">
    <h1 class="page__title">Location Search</h1>
    <SearchLocation />
    <LocationList :locations="[]" />
  </div>
</template>

<script setup lang="ts">
import SearchLocation from '@/features/search-location/SearchLocation.vue'
import LocationList from '@/widgets/location-list/LocationList.vue'
</script>

<style lang="scss" scoped>
.page {
  min-height: 100vh;
  background-color: #f8fafc;
  padding: 24px 16px;

  &__title {
    text-align: center;
    font-size: 32px;
    font-weight: 700;
    color: #1e293b;
    margin: 0 0 32px;
  }
}
</style> 