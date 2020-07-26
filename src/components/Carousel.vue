<template>
   <v-carousel cycle hide-delimiters="" class="d-none">
      <v-carousel-item
        v-for="(item,i) in items"
        :key="i"
        :src="item.src"
        reverse-transition="fade-transition"
        transition="fade-transition"
      >
        <v-row
          class="fill-height"
          align="center"
          justify="center"
        >
          <div class="display-3">{{ slides[i] }} Slide</div>
        </v-row>
      </v-carousel-item>
    </v-carousel>
</template>

<script>
    export default {
        name: 'Carousel'
    }
</script>