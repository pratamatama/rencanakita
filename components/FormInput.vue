<script setup lang="ts">
import { useField } from 'vee-validate'

const props = defineProps<{
  name: string
  label: string
  type?: string
  placeholder?: string
  disabled?: boolean
  value?: string | number
}>()

const name = toRef(props, 'name')

const {
  value: inputValue,
  errorMessage,
  handleBlur,
  handleChange,
} = useField(name, undefined, {
  initialValue: props.value,
})
</script>

<template>
  <label class="block">
    <span class="text-sm">{{ label }}</span>
    <BaseInput
      class="mt-1"
      :id="name"
      :type="type"
      :value="inputValue"
      :disabled="disabled"
      :placeholder="placeholder"
      @update:model-value="handleChange"
      @blur="handleBlur"
    />
    <span class="text-sm text-red-600">{{ errorMessage }}</span>
  </label>
</template>
