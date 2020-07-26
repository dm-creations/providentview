<template>
<div>
    <hero></hero>

    <carousel></carousel>
    
    <our-company></our-company> 
    
    <what-we-do></what-we-do>

</div>
</template>

<script>
// @ is an alias to /src
import WhatWeDo from '../components/WhatWeDo.vue'
import Hero from '../components/Hero.vue'
import Carousel from '../components/Carousel.vue'
import OurCompany from '../components/OurCompany.vue'

export default {
  name: 'Home',
  components: {
    Hero,
    Carousel,
    WhatWeDo,
    OurCompany
  },
  data () {
      return {
        items: [
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/squirrel.jpg',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/sky.jpg',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/bird.jpg',
          },
          {
            src: 'https://cdn.vuetifyjs.com/images/carousel/planet.jpg',
          },
        ],
        slides: [
          'First',
          'Second',
          'Third',
          'Fourth',
          'Fifth'
        ]
      }
    },
}
</script>
