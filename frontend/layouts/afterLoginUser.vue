<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" fixed app>
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <NuxtLink to="/">
        <v-img
          :src="require(`~/assets/RNR_logo.jpg`)"
          max-height="60"
          max-width="60"
        />
      </NuxtLink>
      <v-spacer />
      <v-btn nuxt to="/" color="secondary"> Wyloguj się </v-btn>
    </v-app-bar>
    <v-main>
      <v-container fluid>
        <nuxt />
      </v-container>
    </v-main>
    <v-footer app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      items: [
        {
          icon: 'mdi-apps',
          title: 'Panel użytkownika',
          to: '/user',
        },
        {
          icon: 'mdi-cash',
          title: 'Stan konta',
          to: '/user/srodki',
        },
      ],
      drawer: false,
      title: "Rak n' Roll",
    }
  },
}
</script>
