<template>
  <v-row>
    <v-col>
      <v-card>
        <v-card-title>
          Masz łącznie {{ invoices.length }} zrealizowanych faktur.
        </v-card-title>
      </v-card>
      <v-card v-for="invoice in invoices" :key="invoice.title">
        <v-card-title>
          {{ invoice.title }}
        </v-card-title>
        <v-list-item>
          <v-list-item-icon>
            <v-icon>mdi-cash</v-icon>
          </v-list-item-icon>
          <v-list-item-subtitle>{{ invoice.amount }} PLN</v-list-item-subtitle>
        </v-list-item>

        <v-list-item>
          <v-list-item-icon>
            <v-icon>mdi-date</v-icon>
          </v-list-item-icon>
          <v-list-item-subtitle>
            {{ invoice.date.toString() }}
          </v-list-item-subtitle>
        </v-list-item>
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
      invoices: [
        {
          title: 'Faktura 1',
          amount: randomNumber(10, 99999) + randomNumber(0, 100) / 100,
          date: new Date(randomNumber(1543459675000, 1606618090000)),
        },
        {
          title: 'Faktura 2',
          amount: randomNumber(10, 99999) + randomNumber(0, 100) / 100,
          date: new Date(randomNumber(1543459675000, 1606618090000)),
        },
        {
          title: 'Faktura 3',
          amount: randomNumber(10, 99999) + randomNumber(0, 100) / 100,
          date: new Date(randomNumber(1543459675000, 1606618090000)),
        },
        {
          title: 'Faktura 4',
          amount: randomNumber(10, 99999) + randomNumber(0, 100) / 100,
          date: new Date(randomNumber(1543459675000, 1606618090000)),
        },
        {
          title: 'Faktura 5',
          amount: randomNumber(10, 99999) + randomNumber(0, 100) / 100,
          date: new Date(randomNumber(1543459675000, 1606618090000)),
        },
        {
          title: 'Faktura 6',
          amount: randomNumber(10, 99999) + randomNumber(0, 100) / 100,
          date: new Date(randomNumber(1543459675000, 1606618090000)),
        },
        {
          title: 'Faktura 7',
          amount: randomNumber(10, 99999) + randomNumber(0, 100) / 100,
          date: new Date(randomNumber(1543459675000, 1606618090000)),
        },
        {
          title: 'Faktura 8',
          amount: randomNumber(10, 99999) + randomNumber(0, 100) / 100,
          date: new Date(randomNumber(1543459675000, 1606618090000)),
        },
        {
          title: 'Faktura 9',
          amount: randomNumber(10, 99999) + randomNumber(0, 100) / 100,
          date: new Date(randomNumber(1543459675000, 1606618090000)),
        },
        {
          title: 'Faktura 10',
          amount: randomNumber(10, 99999) + randomNumber(0, 100) / 100,
          date: new Date(randomNumber(1543459675000, 1606618090000)),
        },
      ],
    }
  },
}

function randomNumber(min, max) {
  const r = Math.random() * (max - min) + min
  return Math.floor(r)
}
</script>
