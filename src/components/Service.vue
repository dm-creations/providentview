<template>
    <div 
            class="text-center"
            :style="styles">
      <h2 class="display-2 font-weight-medium mb-3">{{response.name}}</h2>
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
              {{response.content.body}}
      </v-responsive>
    </div>
</template>

<script>
    export default {
        name: 'Service',

        props: {
            space: {
                type: [Number, String],
                default: 96,
            },
            response: {
                type: [Object]
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
            }
        },
        data() {
            return {
            }
        }
    }
</script>