<template>
  <v-app>
    <v-app-bar app color="primary">
      <v-app-bar-title>Vuetify Dashboard</v-app-bar-title>
      <v-btn rounded>Home</v-btn>
      <v-btn rounded>Login</v-btn>
    </v-app-bar>
    <v-main>
      <v-card width="400" class="mx-auto mt-8">
        <v-card-title>
          <h1 class="display-1">Login</h1>
        </v-card-title>
        <v-card-text>
          <v-form>
            <v-text-field label="Username" prepend-icon="mdi-account-circle" />
            <v-text-field :type="showPassword ? 'text' : 'password'" label="Password" prepend-icon="mdi-lock"
              :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'" @click:append="showPassword = !showPassword" />
          </v-form>
          <v-divider></v-divider>
          <v-card-actions>
            <v-btn color="info">Register</v-btn>
            <v-spacer></v-spacer>
            <v-btn color="success">Login</v-btn>
          </v-card-actions>
        </v-card-text>
      </v-card>
    </v-main>
    <v-footer color="primary flex-column" app>{{ new Date().getFullYear() }} - Vuetify Dashboard</v-footer>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  components: {
  },
  data: () => ({
    showPassword: false,
  }),
}
</script>
