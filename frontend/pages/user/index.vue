<template>
  <div style="height: 100%">
    <v-row id="main_row">
      <v-col>
        <v-card tile color="green lighten-1" to="/user/srodki">
          <v-row>
            <v-col>
              <v-card-title class="text-h2">Pieniądze na koncie</v-card-title>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card-text class="text-h3" style="text-align: center">
                {{ balance }} PLN
              </v-card-text>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card-text class="text-h6" style="text-align: center">
                Kliknij i sprawdź, jak możesz pozyskać środki
              </v-card-text>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
      <v-col>
        <v-card tile color="deep-purple lighten-1" to="/user/faktury">
          <v-row>
            <v-col>
              <v-card-title class="text-h2">Lista faktur</v-card-title>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card-text class="text-h3" style="text-align: center">
                Łącznie {{ amountOfInvoices }} faktur
              </v-card-text>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card-text class="text-h6" style="text-align: center">
                Przejrzyj szczegóły
              </v-card-text>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
    <v-row id="main_row">
      <v-col>
        <v-card tile color="blue-grey lighten-1" to="">
          <v-row>
            <v-col>
              <v-card-title class="text-h2">Wiadomości</v-card-title>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card-text class="text-h3" style="text-align: center">
                Masz {{ amountOfMessages }} nieodebranych wiadomości
              </v-card-text>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card-text class="text-h6" style="text-align: center">
                Kliknij by sprawdzić twoje wiadomości
              </v-card-text>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
      <v-col>
        <v-card tile color="light-blue lighten-1" to="">
          <v-row>
            <v-col>
              <v-card-title class="text-h2">Pieniądze na koncie</v-card-title>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card-text class="text-h3" style="text-align: center">
                {{ balance }} PLN
              </v-card-text>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card-text class="text-h6" style="text-align: center">
                Kliknij i sprawdź, jak możesz pozyskać środki
              </v-card-text>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  layout: 'afterLoginUser',
  data() {
    return {
      // mock data
      balance: 399.99,
      amountOfInvoices: 10,
      amountOfMessages: 5,
    }
  },
}
// export default {
//   middleware: 'auth',
// }
</script>

<style scoped>
.v-card {
  height: 100%;
}
.v-card__title {
  color: rgb(255, 255, 255);
  justify-content: center;
}
.v-card__text {
  color: rgb(255, 255, 255) !important;
  justify-content: center;
}
#main_row {
  height: 50%;
}
</style>

<style>
.container {
  height: 100% !important;
}
</style>
