<template>
    <div>
        <hero></hero>
        <v-container              
          v-for="(story,i) in response"
          :key="story.id"
          :title="story.name"
          :content="story.content.body"
        >
                <service :response="response[i]"></service>
        </v-container>
    </div>
</template>

<script>
    import StoryblokClient from 'storyblok-js-client';
    import Hero from '../components/Hero.vue';
    import Service from '../components/Service.vue';

    export default {
        name: 'Services',
        components: {
            Hero,
            Service
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
                .get( this.Link , {
                    version: 'published',
                    "starts_with": "services/"
                })
                .then((response) => {
                    console.log(response)
                    this.response = response.data.stories
                })
                .catch((error) => {
                    console.log(error);
                })
        },
        data() {
            return {
                response: null,
                Link: 'cdn/stories',
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