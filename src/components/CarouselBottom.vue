<template>
<v-container fluid ma-0 pa-0> 
  <v-carousel
    cycle 
    height="454"
    hide-delimiter-background
    show-arrows-on-hover
  >
    <v-carousel-item
      v-for="(slide, i) in slides"
      :key="i"
    >
      <v-sheet
        :color="colors[i]"
        height="100%"
      >
        <v-row
          class="fill-height"
          align="center"
          justify="center"
        >
          <div align="center">
            <h1 class="display-2 ma-4" v-text="slides[i]"></h1>
            <span v-text="texts[i]"></span>
          </div>
        </v-row>
      </v-sheet>
    </v-carousel-item>
  </v-carousel>
</v-container>
</template>

<script>
  export default {
    name: 'CarouselBottom',

    data: () => ({
        colors: [
          'indigo',
          'warning',
          'pink darken-2',
          'red lighten-1',
          'deep-purple accent-4',
        ],
        slides: [
          'LOREM IPSUM DOLOR SIT',
          'Second',
          'Third',
          'Fourth',
          'Fifth',
        ],
        texts: [
          "Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since."
        ]
    }),
  }
</script>
