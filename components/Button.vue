<script setup lang="ts">
defineProps<{
   /**
   * ボタンに表示するテキスト
   */
  label: string
  variant?: 'plain' | 'outlined' | 'tonal' | 'text'
  color: 'primary' | 'success' | 'error' | 'info'
  rounded?:boolean
  flat?: boolean
  exact?: boolean
  elevation?: string | number
  disabled?: boolean
  height?: string | number
  href?: string
  icon?: any
  loading?: string | boolean
}>()
const emits = defineEmits<{
  /**
   * @param label The label of the button
   */
  click: [label: string];
}>()

const onClick = () => {
    emits('click', 'Event')
}
</script>

<template>
  <v-btn
    :label="label"
    :color="color"
    :variant="variant"
    :flat="flat"
    :exact="exact"
    :elevation="elevation"
    :disabled="disabled"
    :router="rounded"
    @click="onClick"
  >
    {{ label }}
  </v-btn>
</template>