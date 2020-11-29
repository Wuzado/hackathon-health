<template>
  <div>
    <v-row justify="center" align="center">
      <v-col cols="12" sm="8" md="6">
        <v-card>
          <v-card-title class="headline justify-center">
            Zaloguj się jako:
          </v-card-title>
          <v-card-actions class="justify-space-around">
            <v-btn color="primary" nuxt to="/user/login">
              <v-icon>mdi-account</v-icon> Użytkownik
            </v-btn>
            <v-btn color="primary" @click="snackbar = true">
              <v-icon>mdi-hand-heart</v-icon> Opiekun
            </v-btn>
            <v-btn color="primary" @click="snackbar = true">
              <v-icon>mdi-lock</v-icon> Administrator
            </v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
    <v-snackbar v-model="snackbar">
      {{ text }}

      <template v-slot:action="{ attrs }">
        <v-btn color="pink" text v-bind="attrs" @click="snackbar = false">
          Zamknij
        </v-btn>
      </template>
    </v-snackbar>
  </div>
</template>

<script>
export default {
  data: () => ({
    snackbar: false,
    text: `Jeszcze nie zaimplementowane!`,
  }),
}
</script>
