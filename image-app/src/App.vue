<script setup>
  import SideBar from './components/SideBar.vue';
  import ImageGallery from './components/ImageGallery.vue';
  import { ref } from "vue"

  const isWithColor = ref(true)
  const onSelectOption = (isColor) => {
    isWithColor.value = isColor
  }
</script>
<template>
  <v-app>
    <SideBar @select-option="onSelectOption"/>
    <v-main>
      <ImageGallery :isWithColor="isWithColor"/>
    </v-main>
  </v-app>
</template>
<style scoped>
  >>> .red-icon .v-icon {
    color: gold;
  }
</style>
