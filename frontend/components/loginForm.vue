<template>
  <v-form v-model="valid">
    <v-container>
      <v-row justify="center" align="center">
        <v-col cols="12" md="4">
          <v-text-field
            v-model="userInfo.username"
            :rules="usernameRules"
            label="Nazwa użytkownika"
            required
          ></v-text-field>
        </v-col>

        <v-col cols="12" md="4">
          <v-text-field
            v-model="userInfo.password"
            :rules="passwordRules"
            label="Hasło"
            required
          ></v-text-field>
        </v-col>
      </v-row>
      <v-row justify="center" align="center">
        <v-col cols="12" md="4">
          <v-btn :disabled="!valid" @click="submit(userInfo)">
            Zaloguj się
          </v-btn>
        </v-col>
      </v-row>
    </v-container>
  </v-form>
</template>

<script>
export default {
  data() {
    return {
      valid: false,
      userInfo: {
        username: '',
        password: '',
      },
      usernameRules: [(v) => !!v || 'Nazwa użytkownika jest wymagana'],
      passwordRules: [(v) => !!v || 'Hasło jest wymagane'],
    }
  },
  methods: {
    submit(userInfo) {
      this.$emit('submitForm', userInfo)
    },
  },
}
</script>
