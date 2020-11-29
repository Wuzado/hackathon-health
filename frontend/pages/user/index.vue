<template>
  <div style="height: 100%">
    <v-row id="main_row">
      <v-col>
        <v-card tile color="green lighten-1" to="/user/srodki">
          <v-row>
            <v-col>
              <v-card-title class="text-h2 text-center">
                Pieniądze na koncie
              </v-card-title>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card-text class="text-h3 text-center">
                {{ balance }} PLN
              </v-card-text>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card-text class="text-h6 text-center">
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
              <v-card-title class="text-h2 text-center">
                Lista faktur
              </v-card-title>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card-text class="text-h3 text-center">
                Łącznie {{ amountOfInvoices }} faktur
              </v-card-text>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card-text class="text-h6 text-center">
                Przejrzyj szczegóły
              </v-card-text>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
    </v-row>
    <v-row id="main_row">
      <v-col>
        <v-card tile color="blue-grey lighten-1" @click="snackbar = true">
          <v-row>
            <v-col>
              <v-card-title class="text-h2 text-center">
                Wiadomości
              </v-card-title>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card-text class="text-h3 text-center">
                Masz {{ amountOfMessages }} nieodebranych wiadomości
              </v-card-text>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card-text class="text-h6 text-center">
                Kliknij by sprawdzić twoje wiadomości
              </v-card-text>
            </v-col>
          </v-row>
        </v-card>
      </v-col>
      <v-col>
        <v-card tile color="light-blue lighten-1">
          <v-row>
            <v-col>
              <v-card-title class="text-h2 text-center">
                Twoja umowa z fundacją kończy się:
              </v-card-title>
            </v-col>
          </v-row>
          <v-row>
            <v-col>
              <v-card-text class="text-h3 text-center">
                {{ endDate.getDate() }}/{{ endDate.getMonth() + 1 }}/{{
                  endDate.getFullYear()
                }}
              </v-card-text>
            </v-col>
          </v-row>
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
  layout: 'afterLoginUser',
  data() {
    return {
      // mock data
      balance: 399.99,
      amountOfInvoices: 10,
      amountOfMessages: 5,
      snackbar: false,
      text: `Jeszcze nie zaimplementowane!`,
      endDate: new Date(2022, 0, 1),
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
