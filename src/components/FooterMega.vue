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
                <v-subheader class="title">
                    SERVICES
                </v-subheader>
                <v-list-item
                      v-for="service in services"
                      :key="service">
                    <v-list-item-content>
                        <v-list-item-title>&rsaquo; {{ service }}</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-col>

            <v-col
              cols="12"
              md="4"
            >
                <v-subheader class="title">
                    INFORMATION
                </v-subheader>
                <v-list-item
                      v-for="info in information"
                      :key="info">
                    <v-list-item-content>
                        <v-list-item-title>&rsaquo; {{ info }}</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-col>
            <v-col
              cols="12"
              md="4"
            >
                <v-subheader class="title">
                    CONTACT
                </v-subheader>
                <v-list-item href="https://api.whatsapp.com/send?phone=07816359993?text=Hi%20I'd%20like%20to%20make%20an%20enquiry%20about%20your%20services" target="_blank">
                    <v-list-item-content>
                        <v-list-item-title>&rsaquo; WhatsApp</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
                <v-list-item>
                    <v-list-item-content>
                        <v-list-item-title >&rsaquo; Facebook Messenger</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
                <v-list-item>
                    <v-list-item-content>
                        <v-list-item-title >&rsaquo; Email</v-list-item-title>
                    </v-list-item-content>
                </v-list-item>
            </v-col>

            <v-col
              class="d-none"
              cols="12"
              md="4"
            >
              <h2 class="text-uppercase title font-weight-bold mb-1 text-left white--text">Contact Us</h2>
            </v-col>
          </v-row>
          

          <v-row>
            <v-col
              cols="12"
              md="12"
              class="text-center"
            >
                <p class="white--text"><strong>Provident View LTD</strong> is registered as a limited company in England and Wales under company number 10440118</p>
                <p>providentview.co.uk &copy; {{ new Date().getFullYear() }} </p>
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
    },
    props: {
      space: {
        type: [Number, String],
        default: 32,
      },
    },
    computed: {
        styles () {
            const space = this.$vuetify.breakpoint.mdAndUp
            ? this.space
            : this.space / 2

            return {
                //   ...this.measurableStyles,
                padding: `${space}px 0 0 0`,
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
            services: [
                'Guaranteed Rent',
                'Assisted Property Search',
                'Providing Tenants',
                'Property Management',
                'Property Maintenance',
                'Tenancy Agreements',
                'Videocall Viewings',
                'Inventory',
                'Marketing',
                'Landlords',
                'Tenant Buyers'
            ],
            information: [
                'How to Buy from abroad', 
                'What type of Mortgage should I get?', 
                'What are the rules for buying in the UK', 
                'How much work goes into Buy to Let', 
                'Tenants leave a review'
            ]
        }
    },

  }
</script>

<style lang="sass">
  #info-alt a
    text-decoration: none
</style>
