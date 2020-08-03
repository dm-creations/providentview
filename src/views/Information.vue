<template>
    <div>
        <hero></hero>
        <v-expansion-panels>
            <v-container 
                class="text-center"
                :style="styles">
                <v-spacer></v-spacer>
                <h2 class="display-2 font-weight-medium mb-3">{{ page }}</h2>
                <v-responsive
                    class="mx-auto mb-8"
                    width="56"
                >
                    <v-divider class="mb-1"></v-divider>
                    <v-divider></v-divider>
                </v-responsive>
            </v-container>
            <v-expansion-panel
            v-for="(story) in response"
            :key="story.id"
            :title="story.name"
            >
                <v-expansion-panel-header>{{story.name}}</v-expansion-panel-header>
                <v-expansion-panel-content>
                  {{story.content.intro}} 
                </v-expansion-panel-content>
        </v-expansion-panel>
  </v-expansion-panels>
    </div>
</template>

<script>
    import Hero from '../components/Hero.vue';
    import StoryblokClient from 'storyblok-js-client';

    export default {
        name: 'Information',
        components: {
            Hero
        },
        computed: {
            styles () {
                const space = this.$vuetify.breakpoint.mdAndUp
                    ? this.space
                    : this.space / 2
                return {
                    //   ...this.measurableStyles,
                    padding: `${space/2}px 0 ${space/2}px 0`,
                }
            }
        },
        created(){
            const Storyblok = new StoryblokClient({
                accessToken: 'HwFlcyigw6QR03f4FrmYNgtt',
                cache: {
                    clear: 'auto',
                    type: 'memory'
                }
            });
            Storyblok
                .get( this.faqLink , {
                    version: 'published',
                    "starts_with": "faqs/"
                })
                .then((response) => {

                    this.response = response.data.stories
                })
                .catch((error) => {
                    console.log(error);
                })
        },
        data() {
            return {
                page: 'FAQs',
                response: null,
                scl: StoryblokClient,
                faqLink: 'cdn/stories',
                stories: [
                    {
                        id: '001',
                        title: 'My nem id Jeff',
                        previewText: 'One day there wa a Jeff, Read More...'
                    },
                    {
                        id: '002',
                        title: 'My nem is Geoffrey',
                        previewText: 'One day there was a Geoffrey oh yes, Read More...'
                    }
                ]
            }
        },
        methods: {
            loadStory() {
                const Storyblok = new StoryblokClient({
                        accessToken: 'HwFlcyigw6QR03f4FrmYNgtt',
                        cache: {
                            clear: 'auto',
                            type: 'memory'
                        }
                    });
                    Storyblok
                        .get( this.link1 , {
                            version: 'published'
                        })
                        .then((response) => {
                            console.log("hi")
                            console.log(response);
                        })
                        .catch((error) => {
                            console.log(error);
                        })
            },
            fetchAPIData() {
                this.responseAvailable = false;
                fetch("https://api.storyblok.com/", {
                    "method": "GET",
                    "headers": {
                        "x-rapidapi-host": "jokes-database.p.rapidapi.com",
                        "x-rapidapi-key": this.apiKey
                    }
                })
                .then(response => { 
                    if(response.ok){
                        return response.json()    
                    } else{
                        alert("Server returned " + response.status + " : " + response.statusText);
                    }                
                })
                .then(response => {
                    this.result = response.body; 
                    this.responseAvailable = true;
                })
                .catch(err => {
                    console.log(err);
                });
            }
        },
        props: {
            space: {
                type: [Number, String],
                default: 96,
            }
        }
    }
</script>