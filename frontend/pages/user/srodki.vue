<template>
  <v-row style="height: 100%">
    <v-col>
      <v-card>
        <v-card-title>
          Możesz zbierać fundusze poniższymi metodami:
        </v-card-title>
        <v-expansion-panels>
          <v-expansion-panel>
            <v-expansion-panel-header> Przelew </v-expansion-panel-header>
            <v-expansion-panel-content>
              <pre>{{ methodsOfPayments.przelew }} </pre>
            </v-expansion-panel-content>
          </v-expansion-panel>
          <v-expansion-panel>
            <v-expansion-panel-header>
              Przelew z zagranicy
            </v-expansion-panel-header>
            <v-expansion-panel-content>
              <pre>{{ methodsOfPayments.przelewZagranica }} </pre>
            </v-expansion-panel-content>
          </v-expansion-panel>
          <v-expansion-panel>
            <v-expansion-panel-header> PayPal </v-expansion-panel-header>
            <v-expansion-panel-content>
              Link do PayPal'a:
              <a :href="methodsOfPayments.paypal.url">
                {{ methodsOfPayments.paypal.url }}
              </a>
              <pre>{{ methodsOfPayments.paypal.message }}</pre>
            </v-expansion-panel-content>
          </v-expansion-panel>
          <v-expansion-panel>
            <v-expansion-panel-header> 1% podatku </v-expansion-panel-header>
            <v-expansion-panel-content>
              <pre>{{ methodsOfPayments.onePercent }}</pre>
            </v-expansion-panel-content>
          </v-expansion-panel>
        </v-expansion-panels>
      </v-card>
    </v-col>
    <v-col>
      <v-card
        tile
        color="green lighten-1"
        style="display: grid; align-items: center; height: 100%"
      >
        <v-row>
          <v-col>
            <v-card-title class="text-h2" style="color: rgb(255, 255, 255)">
              Pieniądze na koncie:
            </v-card-title>
          </v-col>
        </v-row>
        <v-row>
          <v-col>
            <v-card-text
              class="text-h3"
              style="text-align: center; color: rgb(255, 255, 255) !important"
            >
              {{ balance }} PLN
            </v-card-text>
          </v-col>
        </v-row>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  layout: 'afterLoginUser',
  data() {
    return {
      // mock data
      methodsOfPayments: {
        przelew:
          'Fundacja Rak’n’Roll Wygraj Życie\nPL27 1600 1462 1893 9704 1000 0023\nz dopiskiem:\n„dla Agi K.”',
        przelewZagranica:
          'Fundacja Rak’n’Roll Wygraj Życie\nIBAN:\n PL27 1600 1462 1893 9704 1000 0023\nBIC:\n PPABPLPK\nz dopiskiem:\n„dla Agi K.”',
        paypal: {
          url:
            'https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=2G5J7SA5J633Y',
          message: 'z dopiskiem: „dla Agi K.”',
        },
        onePercent: 'KRS: 0000 33 88 03\ncel szczegółowy: „dla Agi K.”',
      },
      balance: 399.99,
    }
  },
}
</script>

<style scoped>
.v-card__title {
  justify-content: center;
}
.v-card__text {
  justify-content: center;
}
</style>

<style>
.container {
  height: 100% !important;
}
</style>
