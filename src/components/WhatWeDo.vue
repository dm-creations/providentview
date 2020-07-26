<template>
    <section
            id="features"
            class="grey lighten-3"
        >
        <div class="py-12"></div>

        <v-container class="text-center">
            <h2 class="display-2 font-weight-medium mb-3">OUR SCOPE OF SERVICES</h2>

            <v-responsive
                class="mx-auto mb-12"
                width="56"
            >

                <v-divider class="mb-1"></v-divider>
                <v-divider></v-divider>
                
            </v-responsive>

            <v-row>
                <v-col
                    v-for="({ icon, title, text }, i) in features"
                    :key="i"
                    cols="12"
                    md="4"
                >
                    <v-card
                        class="py-12 px-4"
                        color="grey lighten-5"
                        flat
                    >
                        <v-theme-provider dark>
                        <div>
                            <v-avatar
                            color="primary"
                            size="88"
                            >
                            <v-icon
                                large
                                v-text="icon"
                            ></v-icon>
                            </v-avatar>
                        </div>
                        </v-theme-provider>

                        <v-card-title
                        class="justify-center font-weight-black text-uppercase"
                        v-text="title"
                        ></v-card-title>

                        <v-card-text
                        class="subtitle-1"
                        v-text="text"
                        >
                    </v-card-text>
                </v-card>
                </v-col>
            </v-row>
            </v-container>

            <div class="py-12"></div>
    </section>
</template>
<script>
export default {
  name: 'WhatWeDo',
  data() {
      return {
          features: [
          {
            icon: 'mdi-home-search',
            title: 'Find Houses',
            text: 'If you are looking to buy in the UK -whether from the UK, or from abroad- we work rigorously to create a criteria for your ideal property and set up a system of regular communication direct to your email. Moving forwards we get you in touch with the right professionals to handle the pre-buying, buying and move-in or setup process.',
          },
          {
            icon: 'mdi-home-currency-usd',
            title: 'Investments',
            text: 'For those who are looking for a way to keep their money working for them with less personal active Real Estate involvement, our investment solutions may be the right option for you.',
          },
          {
            icon: 'mdi-home-edit',
            title: 'Management',
            text: 'We have an established network of professionals to handle each type of management scenario as they arise, to guarantee you a smooth property management journey. We pull from our years of experience and innovation in the rental market to provide the best tailored property management strategy for you and your property.',
          },
        ]
      }
  }
}
</script>