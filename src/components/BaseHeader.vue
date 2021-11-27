<script setup>
import IconYoutube from './icons/IconYoutube.vue'
import IconSearch from './icons/IconSearch.vue'
</script>

<template>
  <header class="flex justify-between p-4 shadow">
    <IconYoutube width="100" height="100" />
    <div class="flex">
      <IconSearch width="28" height="28" />
      <img
        src="https://yt3.ggpht.com/yti/APfAmoGBzdUTzKGi2bU4Wspq-yquIz2dtPk7J4zv0Aiq-J8=s88-c-k-c0x00ffffff-no-rj"
        alt="youtube user image profile"
        class="w-8 rounded-full ml-6"
      />
    </div>
  </header>
</template>
