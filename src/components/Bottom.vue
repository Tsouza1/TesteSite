<template>
  <v-container fluid ma-0 pa-0 class="mt-10">
    <v-sheet class="mx-auto" max-width="1100">
      <span class="font-weight-bold text-h4 px-16">Navegue por Departamento</span>
      <v-slide-group v-model="model" class="pa-4" active-class="success" show-arrows>
        <v-slide-item v-for="n in 15" :key="n">
          <v-card link class="ma-4" elevation="0" height="180" width="128" href>
            <v-img
              src="https://cdn.vuetifyjs.com/images/cards/road.jpg"
              class="white--text align-end"
              gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
            ></v-img>
            <v-card-text align="center" class="justify-center font-weight-black pa-0">
              <div class="subtitle-1 font-weight-medium">Lorem ipsim dolor</div>
            </v-card-text>
          </v-card>
        </v-slide-item>
      </v-slide-group>
    </v-sheet>

    <v-footer color="grey lighten-1" padless>
      <v-row justify="center" class="my-16 px-16 ma-auto">
        <v-col cols="12" sm="6" md="3">
          <span class="font-weight-medium">CENTRAL DE RELACIONAMENTO</span>
          <ul style="list-style: none;">
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim</li>
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim dolor</li>
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim</li>
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim dolor</li>
          </ul>
        </v-col>
        <v-col cols="12" sm="6" md="3">
          <span class="font-weight-medium">LOCALIZAÇÃO</span>
          <ul style="list-style: none;">
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim</li>
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim dolor</li>
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim</li>
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim dolor</li>
          </ul>
        </v-col>
        <v-col cols="12" sm="6" md="3">
          <span class="font-weight-medium">AJUDA</span>
          <ul style="list-style: none;">
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim</li>
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim dolor</li>
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim</li>
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim dolor</li>
          </ul>
        </v-col>
        <v-col cols="12" sm="6" md="3">
          <span class="font-weight-medium">INSTITUCIONAL</span>
          <ul style="list-style: none;">
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim</li>
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim dolor</li>
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim</li>
            <li><v-icon>mdi-menu-right</v-icon>Lorem ipsim dolor</li>
          </ul>
        </v-col>
        <v-col cols="12" sm="6" md="3">
          <v-icon size="40px">mdi-facebook</v-icon>
        </v-col>
        <!-- <v-btn v-for="link in links" :key="link.title" color="white" text rounded class="my-2">{{ link }}</v-btn> -->
      </v-row>
    </v-footer>
    <div class="red py-4 px-16 text-center white--text">
      <v-row class="mx-16">
        <v-col cols="12" sm="6">
          <span
            class="font-weight-light"
          >Albafer - Associação de Bazar e Ferragens do RJ. CNPJ: 02.973.730/001-02</span>
        </v-col>
        <v-col cols="12" sm="6">
          <v-img
            max-height="150"
            max-width="433"
            src="../img/formas-de-pagamento.png"
          ></v-img>
        </v-col>
      </v-row>
    </div>
  </v-container>
</template>

<script>
export default {
  name: "CarouselBottom",

  data: () => ({})
};
</script>