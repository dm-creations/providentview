<template>
  <v-theme-provider dark>
    <section
      id="info-alt"
      class="grey darken-4"
      :style="styles"
    >
      <v-responsive
        class="mx-auto"
        max-width="1400"
      >
        <v-container fluid>
          <v-row>
            <v-col
              cols="12"
              md="4"
            >
                <div class="text-uppercase title font-weight-bold mb-1 text-left white--text">
                    <h2>Provident View LTD</h2>
                    <p>Company Number 10440118</p>
                </div>
            </v-col>

            <v-col
              cols="12"
              md="4"
            >
              <h2 class="text-uppercase title font-weight-bold mb-1 text-left white--text">FAQs</h2>

              <base-business-contact dense />
            </v-col>

            <v-col
              cols="12"
              md="4"
            >
              <h2 class="text-uppercase title font-weight-bold mb-1 text-left white--text">Contact Us</h2>
              <info-features></info-features>
            </v-col>

            <v-col
              cols="12"
              md="12"
            >
              <instagram />
            </v-col>
          </v-row>
        </v-container>
      </v-responsive>
    </section>
  </v-theme-provider>
</template>

<script>
  export default {
    name: 'SectionBusinessInfo',

    components: {
      InfoFeatures: () => import('@/components/InfoFeatures'),
      Instagram: () => import('@/components/Instagram'),
    },
    props: {
      space: {
        type: [Number, String],
        default: 96,
      },
    },
    computed: {
        styles () {
            const space = this.$vuetify.breakpoint.mdAndUp
            ? this.space
            : this.space / 2

            return {
                //   ...this.measurableStyles,
                padding: `${space}px 0`,
            }
        },
    },
    data() {
        return {
            business: [
                {
                    icon: 'mdi-map-marker-outline',
                    title: 'Address',
                    text: '8553 N. Beach St. Ste. 227<br>Fort Worth, Texas 76137',
                },
                {
                    icon: 'mdi-cellphone',
                    title: 'Phone',
                    text: '01 (800) 433 744<br>01 (800) 433 633',
                },
                {
                    icon: 'mdi-email',
                    title: 'Email',
                    text: 'john@vuetifyjs.com<br>heather@vuetifyjs.com',
                },
            ],
        }
    },

  }
</script>

<style lang="sass">
  #info-alt a
    text-decoration: none
</style>
