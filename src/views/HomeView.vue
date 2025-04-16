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
