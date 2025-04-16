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

<style lang="scss" scoped>
.clothes-item {
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 8px;
  border: 1px solid #ececec;
  cursor: pointer;
  span {
    font-size: 18px;
  }
  &--big {
    height: 100%;
  }
}
</style>
