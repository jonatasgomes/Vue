<script setup>
  import { defineEmits } from "vue"

  const emits = defineEmits(["selectOption"])
  const selectOption = (isColor) => {
    emits("selectOption", isColor)
  }
</script>
<template>
  <v-navigation-drawer expand-on-hover rail permanent>
    <v-list>
      <v-list-item prepend-avatar="../../public/photo_jonatas.jpg" subtitle="jonatasgomes@gmail.com"
        title="Jonatas Gomes"></v-list-item>
    </v-list>
    <v-divider></v-divider>
    <v-list density="compact" nav>
      <v-list-item prepend-icon="mdi-format-color-fill" title="Color Gallery" value="color" class="red-icon" @click="selectOption(true)"></v-list-item>
      <v-list-item prepend-icon="mdi-invert-colors" title="Grayscale Gallery" value="gray" @click="selectOption(false)"></v-list-item>
    </v-list>
  </v-navigation-drawer>
</template>