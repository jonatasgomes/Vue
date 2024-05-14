<template>
  <v-app>
    <v-main>
      <v-card>
        <v-row class="ma-0 pa-0">
          <v-col cols="6" class="bg-blue-grey-lighten-2">
            <v-img src="./assets/logo.png" :width="500" cover></v-img>
            <h1 class="text-center">Vuetify Company</h1>
          </v-col>
          <v-col cols="6" class="bg-blue-grey-darken-3 d-flex flex-column justify-center align-center">
            <div>
              <div>
                <h2>Jonatas Gomes</h2>
                <p>CEO, Story Teller Company</p>
              </div>
              <div class="d-flex pt-4">
                <v-icon class="mr-2">mdi-phone</v-icon>
                <p>(X78) 228 216X</p>
              </div>
              <div class="d-flex pt-4">
                <v-icon class="mr-2">mdi-map-marker</v-icon>
                <p>Ontario, Canada</p>
              </div>
              <div class="d-flex pt-4">
                <v-icon class="mr-2">mdi-email</v-icon>
                <p>jg@gmail.com</p>            
              </div>
            </div>
          </v-col>
        </v-row>
      </v-card>
    </v-main>
  </v-app>
</template>
