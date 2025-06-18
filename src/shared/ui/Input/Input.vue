<template>
  <div class="input-wrapper">
    <input
      :value="modelValue"
      :placeholder="placeholder"
      class="input"
      @input="
        $emit('update:modelValue', ($event.target as HTMLInputElement).value)
      "
    />
  </div>
</template>

<script setup lang="ts">
interface IInputProps {
  modelValue: string;
  placeholder?: string;
}

defineProps<IInputProps>();

defineEmits<{
  (e: "update:modelValue", value: string): void;
}>();
</script>

<style lang="scss" scoped>
.input-wrapper {
  width: 100%;
}

.input {
  width: 100%;
  padding: 12px 16px;
  border: 2px solid #e2e8f0;
  border-radius: 8px;
  font-size: 16px;
  transition: border-color 0.2s ease;
  outline: none;

  &:focus {
    border-color: #3b82f6;
  }

  &::placeholder {
    color: #94a3b8;
  }
}
</style>
