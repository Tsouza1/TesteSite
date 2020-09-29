<template>
  <v-container fluid ma-0 pa-0>
    <nav fixed>
      <v-toolbar class="red darken-4" max-width="100%" height="90px">
        <v-toolbar-title>
          <span class="text-h2 font-weight-black white--text">CityLar</span>
        </v-toolbar-title>
        <v-spacer></v-spacer>

        <v-flex xs5 class="hidden-sm-and-down">
          <v-text-field
            hide-details
            dense
            class="mx-10"
            max-width="100px"
            background-color="white"
            filled
            label="Buscar..."
            append-outer-icon="mdi-magnify"
            color="white"
          ></v-text-field>
        </v-flex>
        <v-spacer></v-spacer>
        <v-toolbar-items class="hidden-sm-and-down">
          <v-btn text>MINHA CONTA</v-btn>

          <v-divider vertical></v-divider>

          <v-btn text>MEUS PEDIDOS</v-btn>

          <v-divider vertical></v-divider>

          <v-btn text>FAVORITOS</v-btn>

          <v-divider vertical></v-divider>
          <v-btn text>
            <v-badge left coler="green">
              <span slot="badge">5</span>
              <v-icon>mdi-cart</v-icon>
            </v-badge>
          </v-btn>
        </v-toolbar-items>
        <v-menu>
          <template v-slot:activator="{ on, attrs }">
            <v-btn text class="hidden-md-and-up white--text" v-bind="attrs" v-on="on">
              <v-icon>mdi-menu</v-icon>
            </v-btn>
          </template>
          <v-list>
            <v-list-item v-for="item in menuitems" :key="item.title">
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-toolbar>
      <v-toolbar class="hidden-md-and-up red darken-4" max-width="100%">
        <v-flex xs12>
          <v-text-field
            hide-details
            dense
            class="mx-10"
            max-width="100px"
            background-color="white"
            filled
            label="Buscar..."
            append-outer-icon="mdi-magnify"
            color="white"
          ></v-text-field>
        </v-flex>
      </v-toolbar>
      <v-divider class="red darken-3"></v-divider>

      <v-toolbar class="hidden-sm-and-down red darken-4" max-width="100%">
        <v-spacer />
        <v-menu open-on-hover offset-y>
          <template v-slot:activator="{ on, attrs }">
            <v-btn class="ma-5" color="grey" dark v-bind="attrs" v-on="on">
              CATEGORIAS
              <v-icon>mdi-chevron-down</v-icon>
            </v-btn>
          </template>
          <v-list>
            <v-list-item v-for="(categoria, index) in categorias" :key="index">
              <v-list-item-title>{{ categoria.title }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>

        <v-menu open-on-hover offset-y>
          <template v-slot:activator="{ on, attrs }">
            <v-btn class="ma-5" color="grey" dark v-bind="attrs" v-on="on">
              MARCAS
              <v-icon>mdi-chevron-down</v-icon>
            </v-btn>
          </template>
          <v-list>
            <v-list-item v-for="(marca, index) in marcas" :key="index">
              <v-list-item-title>{{ marca.title }}</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>

        <v-btn class="white--text" text>OFERTAS</v-btn>

        <v-btn class="white--text" text>SOBRE NÓS</v-btn>

        <v-btn class="white--text" text>TRABALHE CONOSCO</v-btn>

        <v-btn class="white--text" text>NOSSA LOJAS</v-btn>
        <v-spacer />
      </v-toolbar>
    </nav>
  </v-container>
</template>

<script>
export default {
  name: "Header",

  data: () => ({
    categorias: [
      { title: "categoria" },
      { title: "categoria" },
      { title: "categoria" }
    ],
    marcas: [{ title: "marca" }, { title: "marca" }, { title: "marca" }],
    menuitems: [
      { title: "Minha Conta" },
      { title: "Meus Pedidos" },
      { title: "Favoritos" },
      { title: "Carrinho" },
      { title: "Categorias" },
      { title: "Marcas" },
      { title: "Ofertas" },
      { title: "Sobre nós" },
      { title: "Trabalhe conosco" },
      { title: "Nossas Lojas" }
    ]
  })
};
</script>