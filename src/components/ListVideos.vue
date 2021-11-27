<script setup>
import VideoItem from './VideoItem.vue'
defineProps({
  videos: {
    type: Array,
    default: () => [],
  },
})
</script>

<template>
  <section>
    <VideoItem
      v-for="video in videos"
      :key="video.channelName"
      :video="video"
    ></VideoItem>
  </section>
</template>
