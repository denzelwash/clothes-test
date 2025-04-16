<template>
  <div class="selected-clothes">
    <div class="selected-clothes__block selected-clothes__block--multiple">
      <ClothesItem
        v-for="item in selectedItemsLeft"
        :key="item.id"
        :name="item.name"
        type="small"
        @click="removeFromSelectedItemsLeftHandler(item)"
      />
      <div class="selected-clothes__counter">
        selected {{ `${selectedItemsLeft.length} / ${SELECTED_MAX_COUNT_LEFT}` }}
      </div>
    </div>
    <div class="selected-clothes__block selected-clothes__block--single">
      <ClothesItem
        v-if="selectedItemRight"
        :name="selectedItemRight.name"
        type="big"
        @click="removeFromSelectedItemRightHandler"
      />
    </div>
  </div>
  <div class="available-clothes">
    <div class="available-clothes__block">
      <ClothesItem
        v-for="item in availableItemsLeft"
        :key="item.id"
        :name="item.name"
        :type="selectedItemsLeft.length === SELECTED_MAX_COUNT_LEFT ? 'disabled' : 'default'"
        @click="addToSelectedItemsLeftHandler(item)"
      />
    </div>
    <div class="available-clothes__block">
      <ClothesItem
        v-for="item in availableItemsRight"
        :key="item.id"
        :name="item.name"
        :type="selectedItemRight ? 'disabled' : 'default'"
        @click="addToSelectedItemRightHandler(item)"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import ClothesItem from '@/components/ClothesItem.vue'
import type { IClothesItem } from '@/types/clothes'
import { DATA_LEFT, DATA_RIGHT, SELECTED_MAX_COUNT_LEFT } from '@/const'
import { ref, computed } from 'vue'

const selectedItemsLeft = ref<IClothesItem[]>([])
const selectedItemRight = ref<IClothesItem | null>(null)

const availableItemsLeft = computed(() => {
  return DATA_LEFT.filter((c) => !selectedItemsLeft.value.find((s) => c.id === s.id))
})

const availableItemsRight = computed(() => {
  const currentSelected = selectedItemRight.value
  if (currentSelected !== null) {
    return DATA_RIGHT.filter((c) => c.id !== currentSelected.id)
  }
  return DATA_RIGHT
})

const addToSelectedItemsLeftHandler = (clothes: IClothesItem) => {
  if (selectedItemsLeft.value.length < SELECTED_MAX_COUNT_LEFT) {
    selectedItemsLeft.value.push(clothes)
  }
}

const removeFromSelectedItemsLeftHandler = (clothes: IClothesItem) => {
  selectedItemsLeft.value = selectedItemsLeft.value.filter((c) => c.id !== clothes.id)
}

const addToSelectedItemRightHandler = (clothes: IClothesItem) => {
  if (selectedItemRight.value === null) {
    selectedItemRight.value = clothes
  }
}

const removeFromSelectedItemRightHandler = () => {
  selectedItemRight.value = null
}
</script>
