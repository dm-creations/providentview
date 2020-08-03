<template>
<div>
    <hero></hero>

    <our-company></our-company> 
    
    <what-we-do></what-we-do>

</div>
</template>

<script>
// @ is an alias to /src
import WhatWeDo from '../components/WhatWeDo.vue'
import Hero from '../components/Hero.vue'
import OurCompany from '../components/OurCompany.vue'

export default {
  name: 'Home',
  components: {
    Hero,
    WhatWeDo,
    OurCompany
  },
  data () {
      return {
        
      }
    },
}
</script>
