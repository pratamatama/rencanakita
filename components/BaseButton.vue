<script setup lang="ts">
import { emit } from 'process'

const props = defineProps<{
  type?: 'submit' | 'button'
  disabled?: boolean
}>()

const emit = defineEmits(['click'])

const onClick = (e: Event) => {
  if (props.type === 'button') {
    e.preventDefault()
    emit('click')
  }
}
</script>

<template>
  <button
    @click="onClick"
    :disabled="disabled"
    :type="type ?? 'submit'"
    class="bg-blue-500 dark:bg-blue-600 hover:bg-blue-600 dark:hover:bg-blue-700 rounded-lg p-3 px-6 transition-colors duration-200"
  >
    <span class="text-sm font-medium">
      <slot />
    </span>
  </button>
</template>
