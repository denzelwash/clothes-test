<template>
  <main>
    <div class="selected-clothes">
      <div class="selected-clothes__block selected-clothes__block--multiple">
        <ClothesItem :name="'11'" />
        <ClothesItem :name="'11'" />
        <ClothesItem :name="'11'" />
        <ClothesItem :name="'11'" />
        <ClothesItem :name="'11'" />
        <ClothesItem :name="'11'" />
        <ClothesItem :name="'11'" />
        <ClothesItem :name="'11'" />
        <ClothesItem :name="'11'" />
        <ClothesItem :name="'11'" />
        <div class="selected-clothes__counter">selected 1 / 20</div>
      </div>
      <div class="selected-clothes__block selected-clothes__block--single">
        <ClothesItem :name="'11'" />
      </div>
    </div>
    <div class="available-clothes">
      <div class="available-clothes__block">
        <ClothesItem :name="'11'" />
        <ClothesItem :name="'11'" />
        <ClothesItem :name="'11'" />
        <ClothesItem :name="'11'" />
      </div>
      <div class="available-clothes__block">
        <ClothesItem :name="'11'" />
        <ClothesItem :name="'11'" />
        <ClothesItem :name="'11'" />
        <ClothesItem :name="'11'" />
      </div>
    </div>
  </main>
</template>

<script setup lang="ts">
import ClothesItem from '@/components/ClothesItem.vue'
</script>

<style lang="scss">
.selected-clothes {
  display: grid;
  grid-template-columns: 300px 300px;
  justify-content: space-between;
  gap: 16px;
  margin-bottom: 16px;
  &__block {
    position: relative;
    border: 1px solid #ececec;
    min-height: 300px;
    padding: 16px;
    &--multiple {
      display: flex;
      flex-wrap: wrap;
      align-content: flex-start;
      gap: 4px;
      .clothes-item {
        width: calc(100% / 4 - 3px);
        height: calc(100% / 4 - 3px);
      }
    }
    &--single {
      > div {
        height: 100%;
      }
    }
  }
  &__counter {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    padding: 8px;
    text-align: center;
  }
}
.available-clothes {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 16px;
  &__block {
    display: flex;
    flex-wrap: wrap;
    align-content: flex-start;
    gap: 8px;
    border: 1px solid #ececec;
    min-height: 600px;
    padding: 16px;
    .clothes-item {
      width: calc(100% / 4 - 8px);
      height: calc(100% / 4 - 8px);
    }
  }
}
</style>
