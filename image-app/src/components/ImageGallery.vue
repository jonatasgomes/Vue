<script setup>
  import { defineProps } from "vue"

  const p = defineProps(["isWithColor"])
  const copyUrl = async (url) => {
    await navigator.clipboard.writeText(url)
  }
</script>
<template>
  <v-card class="mx-5 my-5" color="black">
    <v-row>
      <v-col v-for="n in 200" cols="4" sm="2">
        <v-card
          hover
          @click="copyUrl(`https://picsum.photos/500/300?image=${n * 5 + 10}${p.isWithColor ? '' : '&grayscale'}`)"
        >
          <v-img
            :src="`https://picsum.photos/500/300?image=${n * 5 + 10}${p.isWithColor ? '' : '&grayscale'}`"
            :lazy-src="`https://picsum.photos/10/6?image=${n * 5 + 10}${p.isWithColor ? '' : '&grayscale'}`"
          >
            <template v-slot:placeholder>
              <v-row class="fill-height ma-0" align="center" justify="center">
                <v-progress-circular indeterminate color="grey-lighten-5"></v-progress-circular>
              </v-row>
            </template>
          </v-img>
        </v-card>
      </v-col>
    </v-row>
  </v-card>
</template>