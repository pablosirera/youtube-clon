<script setup>
import { computed, ref } from '@vue/reactivity'
import Chip from './Chip.vue'

defineProps({
  categories: {
    type: Array,
    default: () => [],
  },
})
const emits = defineEmits(['select-category'])

const categorySelected = ref()
const isAllOptionSelected = computed(() => {
  return !categorySelected.value
})

const checkIfIsSelected = categoryId => {
  return categoryId === categorySelected.value
}
const selectCategory = categoryId => {
  categorySelected.value = categoryId
  emits('select-category', categoryId)
}
</script>

<template>
  <section class="p-2 flex overflow-scroll">
    <Chip
      text="Todo"
      :is-selected="isAllOptionSelected"
      @click="selectCategory(null)"
    />
    <Chip
      v-for="category in categories"
      :key="category.id"
      :text="category.name"
      :is-selected="checkIfIsSelected(category.id)"
      @click="selectCategory(category.id)"
    />
    <Chip
      v-for="category in categories"
      :key="category.id"
      :text="category.name"
    />
  </section>
</template>
