<template>
    <div>
        <hero></hero>

    </div>
</template>

<script>
    import Hero from '../components/Hero.vue';

    export default {
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
        props: {
            space: {
                type: [Number, String],
                default: 96,
            }
        }
    }
</script>