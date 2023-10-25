<template>
  <input type="text" :value="value" @input="emit('update:value', value)" />
</template>
<script lang="ts" setup>
defineProps<{
  value?: string;
}>();
const emit = defineEmits<{
  (event: "update:value", value: string): void;
}>();
</script>
<style lang="postcss" scoped>
input {
  padding: 6px 8px;
  border-radius: 4px;
  border: 1px solid #d1d5db;
}
</style>
