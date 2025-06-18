<template>
  <div class="search-location">
    <Input
      v-model="searchQuery"
      placeholder="Search for a location..."
      class="search-location__input"
      @update:modelValue="handleSearch"
    />
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import Input from '@/shared/ui/Input/Input.vue'

interface ISearchLocationEmits {
  (e: 'search', query: string): void
}

const searchQuery = ref('')
const emit = defineEmits<ISearchLocationEmits>()

const handleSearch = (value: string) => {
  emit('search', value)
}
</script>

<style lang="scss" scoped>
.search-location {
  max-width: 600px;
  margin: 0 auto;
  padding: 24px 16px;

  &__input {
    width: 100%;
  }
}
</style> 