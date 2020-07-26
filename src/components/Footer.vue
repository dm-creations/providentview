<template>
    <v-footer
      color="primary lighten-1"
      padless
    >
      <v-row
        justify="center"
        no-gutters
      >
        <v-btn
          v-for="link in links"
          :key="`${link.label}-footer-link`"
          color="white"
          text
          rounded
          class="my-2"
          :to="link.url"
        >
          {{ link.label }}
        </v-btn>
        <v-col
          class="primary lighten-2 py-4 text-center white--text"
          cols="12"
        >
          {{ new Date().getFullYear() }} — <strong>Vuetify</strong>
        </v-col>
      </v-row>
    </v-footer>
</template>
<script>
export default {
    name: 'HomeFooter',
    props: {
        linkz: {

        }
    },
    data () {
    return {
      links: [
        {
          label: 'Home',
          url: '/'
        },
        {
          label: 'Login',
          url: '/login'
        },
        {
          label: 'About Us',
          url: '/about-us'
        },
        {
          label: 'Sign Up',
          url: '/signup'
        },
        {
          label: 'Dashboard',
          url: '/double-dashboard'
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
  }
}
</script>