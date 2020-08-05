<template>
    <div>
        <hero></hero>
        <v-container>
            <v-row>
                <v-spacer></v-spacer>
                    <v-col
                        cols="12"
                        md="4"
                       >
                        <v-card>
                            <v-subheader class="title">
                                CONTACT
                            </v-subheader>
                            <v-list-item href="https://api.whatsapp.com/send?phone=07816359993?text=Hi%20I'd%20like%20to%20make%20an%20enquiry%20about%20your%20services" target="_blank">
                                <v-list-item-icon>
                                    <v-icon>mdi-whatsapp</v-icon>
                                </v-list-item-icon>
                                <v-list-item-title>WhatsApp</v-list-item-title>
                            </v-list-item>
                            
                            <v-list-item href="m.me/110130504123888">
                                <v-list-item-icon>
                                    <v-icon>mdi-facebook-messenger</v-icon>
                                </v-list-item-icon>
                                <v-list-item-title>Facebook Messenger</v-list-item-title>
                            </v-list-item>

                            <v-list-item href="mailto:info@providentview.co.uk">
                                <v-list-item-icon>
                                    <v-icon>mdi-at</v-icon>
                                </v-list-item-icon>
                                <v-list-item-title>Email</v-list-item-title>
                            </v-list-item>
                        </v-card>
                    </v-col>
                <v-spacer></v-spacer>
            </v-row>
        </v-container>
    </div>
</template>

<script>
    import Hero from '../components/Hero.vue'
    export default {
        name: 'Contact Us',
        components: {
            Hero
        }
    }
</script>

<style lang="scss" scoped>

</style>