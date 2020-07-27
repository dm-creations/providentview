<template>
  <v-app>
    <v-app-bar app color="indigo" dark>
      <v-toolbar-title>Provident View LTD</v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        v-for="link in links"
        :key="`${link.label}-header-link`"
        text 
        rounded 
        :to="link.url">
        {{ link.label }}
      </v-btn>
      <!-- can be an option to add later <v-btn @click="toggleTheme" text rounded>Toggle Theme</v-btn> -->
    </v-app-bar>
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
      links: [
        {
          label: 'Home',
          url: '/'
        },
        {
          label: 'About Us',
          url: '/about-us'
        },
        {
          label: 'Services',
          url: '/services'
        },
        {
          label: 'Contact Us',
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
