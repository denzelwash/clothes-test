<template>
  <div :class="['clothes-item', { 'clothes-item--big': props.type === 'big' }]">
    <span>{{ props.name }}</span>
  </div>
</template>

<script setup lang="ts">
interface Props {
  name: string
  type?: 'default' | 'big'
}
const props = withDefaults(defineProps<Props>(), {
  type: 'default',
})
</script>
