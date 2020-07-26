<template>
    <v-container 
            class="text-center"
            :style="styles">
      <h2 class="display-2 font-weight-medium mb-3">OUR COMPANY</h2>
      <v-responsive
        class="mx-auto mb-8"
        width="56"
      >
      <v-divider class="mb-1"></v-divider>
      <v-divider></v-divider>
      </v-responsive>
      <v-responsive
              class="mx-auto title font-weight-light mb-8"
              max-width="720"
      >
              Provident View LTD is a property management company that has 4+ years of experience operating in London and the South East of England. We aim to provide top quality and well maintained properties to Tenants at affordable prices suitable for professionals. Our counter-aim is to provide high quality, low property-wearing and reliable tenants for Landlords who want to invest in their properties without investing unnecessary time.
      </v-responsive>
    </v-container>
</template>

<script>
    export default {
        name: 'OurCompany',

        props: {
            space: {
                type: [Number, String],
                default: 96,
            }
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
    }
</script>