<script setup lang="ts">
defineProps<{ text?: string }>()
</script>

<template>
  <div class="divider">
    <slot v-if="!text" />
    <template v-else>{{ text }}</template>
  </div>
</template>

<style lang="postcss" scoped>
.divider {
  @apply flex items-center text-sm text-gray-500 dark:text-gray-600;
}

.divider::before,
.divider::after {
  content: '';
  @apply h-px bg-gray-200 dark:bg-gray-700 grow;
}

.divider::before {
  @apply mr-4;
}

.divider::after {
  @apply ml-4;
}
</style>
