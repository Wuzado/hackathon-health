<template>
  <v-row justify="center" align="center">
    <v-col cols="12" md="4">
      <v-card>
        <v-card-title class="justify-center">
          Zaloguj się jako użytkownik
        </v-card-title>
        <div class="justify-center">
          <login-form @submitForm="loginUser($event)"></login-form>
        </div>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
import loginForm from '~/components/loginForm.vue'

export default {
  components: { loginForm },
  /* methods: {
    async loginUser(logininfo) {
      try {
        await this.$auth.loginWith('local', {
          data: logininfo,
        })
        this.$snackbarManager.showMessage({
          content: `Thanks for signing in, ${this.$auth.user}!`,
          color: 'success',
        })
        this.$router.push('/offers');
      } catch (error) {
        this.$snackbarManager.showMessage({
          content: 'There was an issue while signing in. Please try again.',
          color: 'error',
        });
      }
    },
  }, */
}
</script>
