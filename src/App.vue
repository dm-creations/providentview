<template>
  <v-app>
    <v-app-bar app color="indigo" dark>
      <v-app-bar-nav-icon 
        class="hidden-md-and-up"
        @click="drawer = true"></v-app-bar-nav-icon>
      <v-toolbar-title>Provident View LTD</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        v-for="link in links"
        :key="`${link.label}-header-link`"
        class="hidden-md-and-down"
        text 
        rounded 
        :to="link.url">
        {{ link.label }}
      </v-btn>
      <!-- can be an option to add later <v-btn @click="toggleTheme" text rounded>Toggle Theme</v-btn> -->
    </v-app-bar>
    <v-navigation-drawer
      app
      v-model="drawer"
      temporary
    >
      <v-list
        nav
        dense
      >
          <v-list-item v-model="group"
          active-class="deep-purple--text text--accent-4"
          v-for="link in links"
          :key="`${link.label}-header-link`"
          text 
          rounded
          :to="link.url">
            <v-list-item-icon>
              <v-icon>mdi-{{ link.icon }}</v-icon>
            </v-list-item-icon>
            <v-list-item-title>{{ link.label }}</v-list-item-title>
          </v-list-item>

      </v-list>
    </v-navigation-drawer>
    <v-main>
      <router-view></router-view>
    </v-main>
    <fb-messenger></fb-messenger>
    <homefooter></homefooter>
  </v-app>
</template>

<script>
import SectionBusinessInfo from './components/FooterMega.vue'
import FBM from './components/FacebookMessenger.vue'
export default {
  name: 'App',
  components: {
    'homefooter': SectionBusinessInfo ,
    'fb-messenger': FBM
  },
  data () {
    return {
      drawer: false,
      group: null,
      links: [
        {
          label: 'Home',
          icon: 'home',
          url: '/'
        },
        {
          label: 'Information',
          icon: 'information',
          url: '/information'
        },
        {
          label: 'Services',
          icon: 'home-edit',
          url: '/services'
        },
        {
          label: 'Contact Us',
          icon: 'card-account-mail',
          url: '/contact-us'
        }
      ],
    }
  },
  methods: {
    toggleTheme() {
      this.$vuetify.theme.themes.dark.anchor = '#41B883'
      this.$vuetify.theme.dark = !this.$vuetify.theme.dark
    }
  }
}
</script>
