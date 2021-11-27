<script setup>
import { ref } from '@vue/reactivity'
import BaseHeader from './components/BaseHeader.vue'
import ListVideos from './components/ListVideos.vue'
import CategoriesList from './components/CategoriesList.vue'
import videosData from './assets/videos.json'
import categoriesData from './assets/categories.json'

const originalVideos = videosData.data
let filteredVideos = ref(originalVideos)
const categories = categoriesData.data

const selectVideosWithCategory = categoryId => {
  if (!categoryId) {
    filteredVideos.value = originalVideos
    return
  }

  filteredVideos.value = originalVideos.filter(
    video => video.category === categoryId
  )
}
</script>

<template>
  <BaseHeader />
  <CategoriesList
    :categories="categories"
    @select-category="selectVideosWithCategory"
  />
  <ListVideos :videos="filteredVideos" />
</template>
