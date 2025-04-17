<template>
  <div :class="['clothes-item', props.type !== 'default' ? `clothes-item--${props.type}` : '']">
    <span>{{ props.name }}</span>
  </div>
</template>

<script setup lang="ts">
interface Props {
  name: string
  type?: 'default' | 'small' | 'disabled'
}
const props = withDefaults(defineProps<Props>(), {
  type: 'default',
})
</script>
