<script setup lang="ts">
defineProps<{
  type?: string
  placeholder?: string
  disabled?: boolean
  readonly?: boolean
  value?: string | number
}>()

const emit = defineEmits(['update:modelValue', 'blur'])

const onInput = (e: Event) => {
  const value = (e.target as HTMLInputElement).value
  emit('update:modelValue', value)
}
</script>
<template>
  <input
    @input="onInput"
    :value="value"
    :disabled="disabled"
    :readonly="readonly"
    :type="type ?? 'text'"
    :placeholder="placeholder"
    class="block w-full rounded-md bg-white dark:bg-gray-800 p-4 py-3 border border-gray-200 dark:border-gray-700 shadow-sm focus:border-indigo-200 dark:focus:border-indigo-600 focus:ring focus:ring-indigo-200 focus:ring-opacity-50 outline-none"
  />
</template>
