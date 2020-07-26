<template>
<section id="hero">
    <v-img
      :min-height="minHeight"
      :src="require('@/assets/london-tower-bridge-the-shard-lg.jpg')"
      class="white--text"
      gradient="to right, rgba(5, 11, 31, .8), rgba(5, 11, 31, .8)"
      alt="London Tower Bridge &amp; The Shard by Sam Valadi - https://flic.kr/p/rRpmAh"
    >
      <v-container class="fill-height px-4 py-12">
        <v-responsive
          class="d-flex align-center"
          height="100%"
          max-width="700"
          width="100%"
        >
          <h1 class="text-h1">{{ title }}</h1>

          <h2 class="font-weight-light">
            The property management company with a view to your peace of mind.
          </h2>

          <div
            :class="$vuetify.breakpoint.smAndDown ? 'flex-column align-start' : 'align-center'"
            class="d-flex flex-wrap"
          >
            <v-btn color="indigo">
              Discover More
            </v-btn>

            <span class="font-weight-bold ml-6 mr-4 my-4">or</span>

            <v-btn
              :ripple="false"
              class="pa-1"
              text
            >
              Get in Touch
            </v-btn>
          </div>
        </v-responsive>
      </v-container>
    </v-img>
  </section>
</template>

<script>
    export default {
        name: 'Hero',

        data() {
            return {
                title: 'PROVIDENT VIEW'
            }
        },
        provide: {
            theme: { isDark: true },
        },

        computed: {
            minHeight () {
                const height = this.$vuetify.breakpoint.mdAndUp ? '100vh' : '50vh'

                return `calc(${height} - ${this.$vuetify.application.top}px)`
            },
        },
    }
</script>