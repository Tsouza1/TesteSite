<template>
  <v-app>
    <Header/>
     <v-main>
      <CarouselTop/>
      <Content/>
      <CarouselBottom/>
      <Bottom/>
    </v-main>
  </v-app>
</template>

<script>
import Header from './components/Header';
import CarouselTop from './components/CarouselTop';
import Content from './components/Content';
import CarouselBottom from './components/CarouselBottom';
import Bottom from './components/Bottom';

export default {
  name: 'App',

  components: {
    Header,
    CarouselTop,
    Content,
    CarouselBottom,
    Bottom,
  },

  data: () => ({
    //
  }),
};
</script>
