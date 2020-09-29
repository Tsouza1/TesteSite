<template>
  <v-container fluid ma-0 pa-0 class="my-10">
    <v-row class="mx-auto ma-5 rowcenter">
      <v-col v-for="card in cards" :key="card.title" cols="12" sm="6" md="4">
        <v-card flat class="mx-5 my-5 text-xs-center">
          <v-img :src="card.src" class="white--text align-end" height="371px"></v-img>

          <v-card-actions class="justify-center">
            <v-btn
              max-width="208px"
              class="red darken-4 white--text title mt-n7"
              outlined
              text
            >COMPRE JÁ >></v-btn>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>

    <v-sheet class="mx-auto ma-5" max-width="1100">
      <div
        align="center"
        class="navcont red darken-4 white--text font-weight-black headline py-3"
      >Top Vendas a partir de busca</div>
      <v-slide-group v-model="model1" class="pa-4" active-class="red" show-arrows>
        <v-slide-item v-for="card in cards" :key="card.title" v-slot:default="{ active, toggle }">
          <v-card class="ma-4" height="307" width="229" color="#d9c0c2" @click="toggle">
            <v-img
              :src="card.src"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="241px"
            >
              <v-card-title
                class="justify-center white red--text pa-0"
                heigth="10px"
                v-text="card.title"
              ></v-card-title>
            </v-img>
            <v-card-text class="justify-center font-weight-black">
              <div v-show="active ? undefined : 'hidden'" align="center" v-text="card.price"></div>

              <v-rating
                v-show="active ? undefined : 'hidden'"
                align="center"
                background-color="red"
                color="red"
                dense
                readonly
                :value="card.value"
                half-increments
                hover
                size="18"
              ></v-rating>
              <v-row class="fill-height" align="center" justify="center">
                <v-scale-transition>
                  <v-btn link href class="caption" v-if="active">
                    <v-icon>mdi-cart</v-icon>Adicionar ao Carrinho
                  </v-btn>
                </v-scale-transition>
              </v-row>
            </v-card-text>
          </v-card>
        </v-slide-item>
      </v-slide-group>
    </v-sheet>

    <v-sheet class="mx-auto my-10" max-width="1100">
      <span class="font-weight-bold text-h4 my-10">Navegue por Departamento</span>
      <v-slide-group v-model="model" class="pa-4" active-class="success" show-arrows>
        <v-slide-item v-for="card in cards" :key="card.tilte">
          <v-card link class="ma-4" elevation="0" height="180" width="128" href>
            <v-img
              :src="card.src"
              class="white--text align-end"
            ></v-img>
            <v-card-text align="center" class="justify-center font-weight-black pa-0">
              <div class="subtitle-1 font-weight-medium">Lorem ipsim dolor</div>
            </v-card-text>
          </v-card>
        </v-slide-item>
      </v-slide-group>
    </v-sheet>

    <v-row class="mx-auto ma-5 rowcenter text-justify">
      <v-col v-for="info in infos" :key="info.title" cols="12" sm="6" md="4">
        <v-card flat class="text-xs-center">
          <v-card-title>
            <v-icon large left></v-icon>
            <span class="title font-color-red" v-text="info.title"></span>
          </v-card-title>
          <v-card-text v-text="info.text"></v-card-text>
        </v-card>
      </v-col>
    </v-row>

    <v-sheet class="mx-auto ma-5" max-width="1100">
      <div
        align="center"
        class="red darken-4 white--text font-weight-black text-h4 my-10 py-3"
      >OFERTAS</div>
      <v-slide-group v-model="model1" class="pa-4" active-class="red" show-arrows>
        <v-slide-item v-for="card in cards" :key="card.title" v-slot:default="{ active, toggle }">
          <v-card class="ma-4" height="307" width="229" color="#d9c0c2" @click="toggle">
            <v-img
              :src="card.src"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
              height="241px"
            >
              <v-card-title class="justify-center yellow red--text my-n19 pa-0">Desconto 20%</v-card-title>
              <v-card-title
                class="justify-center white red--text pa-0"
                heigth="10px"
                v-text="card.title"
              ></v-card-title>
            </v-img>
            <v-card-text class="justify-center font-weight-black">
              <div v-show="active ? undefined : 'hidden'" align="center" v-text="card.price"></div>

              <v-rating
                v-show="active ? undefined : 'hidden'"
                align="center"
                background-color="red"
                color="red"
                dense
                readonly
                :value="card.value"
                half-increments
                hover
                size="18"
              ></v-rating>
              <v-row class="fill-height" align="center" justify="center">
                <v-scale-transition>
                  <v-btn link href class="caption" v-if="active">
                    <v-icon>mdi-cart</v-icon>Adicionar ao Carrinho
                  </v-btn>
                </v-scale-transition>
              </v-row>
            </v-card-text>
          </v-card>
        </v-slide-item>
      </v-slide-group>
    </v-sheet>

    <v-row dense class="mx-auto ma-5 rowcenter">
      <v-col v-for="categoria in categorias" :key="categoria.title" cols="12" sm="6" md="6">
        <v-card link href class="my-5 mx-8">
          <v-img
            :src="categoria.src"
            class="white--text align-end"
            gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
            height="236px"
          >
            <v-card-title class="red darken-4 cardctg" v-text="categoria.title"></v-card-title>
          </v-img>
        </v-card>
      </v-col>
    </v-row>

    <v-btn
            v-scroll="onScroll"
            v-show="fab"
            fab
            dark
            fixed
            bottom
            right
            color="primary"
            @click="toTop"
          >
            <v-icon>mdi-chevron-up</v-icon>
          </v-btn>

  </v-container>
</template>


<script>
export default {
  name: "Content",

  data: () => ({
    colors: [
      "indigo",
      "warning",
      "pink darken-2",
      "red lighten-1",
      "deep-purple accent-4"
    ],
    slides: ["First", "Second", "Third", "Fourth", "Fifth"],
    cards: [
      {
        title: "Pre-fab homes",
        src: "https://oiguassu.com.br/wp-content/themes/fox/images/placeholder.jpg",
        flex: 4,
        class: "text-decoration-line-through",
        price: "$ 8000",
        pricecut: "$ 10000",
        value: "3"
      },
      {
        title: "Favorite road trips",
        src: "https://oiguassu.com.br/wp-content/themes/fox/images/placeholder.jpg",
        flex: 4,
        price: "$ 10299"
      },
      {
        title: "Best airlines",
        src: "https://oiguassu.com.br/wp-content/themes/fox/images/placeholder.jpg",
        flex: 4,
        price: "$ 8000"
      },
      {
        title: "Best airlines",
        src: "https://oiguassu.com.br/wp-content/themes/fox/images/placeholder.jpg",
        flex: 4,
        price: "$ 10299"
      },
      {
        title: "Best airlines",
        src: "https://oiguassu.com.br/wp-content/themes/fox/images/placeholder.jpg",
        flex: 4,
        price: "$ 8000"
      },
      {
        title: "Best airlines",
        src: "https://oiguassu.com.br/wp-content/themes/fox/images/placeholder.jpg",
        flex: 4,
        price: "$ 10299"
      }
    ],
    infos: [
      {
        title: "Entregamos somente no RJ",
        text:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Quis ipsum suspendisse",
        src: ""
      },
      {
        title: "Atendimento ao Cliente",
        text:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Quis ipsum suspendisse",
        src: ""
      },
      {
        title: "Parcelamos em até 10x",
        text:
          "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Quis ipsum suspendisse",
        src: ""
      }
    ],
    model: null,
    model1: null,
    categorias: [
      {
        title: "Organização da Casa",
        src: "https://oiguassu.com.br/wp-content/themes/fox/images/placeholder.jpg",
        flex: 6
      },
      {
        title: "Ferramentas",
        src: "https://oiguassu.com.br/wp-content/themes/fox/images/placeholder.jpg",
        flex: 6
      },
      {
        title: "Materias de Construção",
        src: "https://oiguassu.com.br/wp-content/themes/fox/images/placeholder.jpg",
        flex: 6
      },
      {
        title: "Utilidades Domésticas",
        src: "https://oiguassu.com.br/wp-content/themes/fox/images/placeholder.jpg",
        flex: 6
      }
    ],
    fab: false
  }),
    methods: {
    onScroll (e) {
      if (typeof window === 'undefined') return
      const top = window.pageYOffset ||   e.target.scrollTop || 0
      this.fab = top > 20
    },
    toTop () {
      this.$vuetify.goTo(0)
    }
  }
};
</script>
<style>
.rowcenter {
  max-width: 1100px;
}
</style>