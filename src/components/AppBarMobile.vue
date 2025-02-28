<template>
    <v-app-bar app color="#252525" elevation="24">
      <v-toolbar-title>
        <a href="/" class="logo-text" aria-label="Ir para a página inicial">
          Curci
          <v-icon class="mr-2 neon-icon" size="45" aria-hidden="true">
            mdi-dev-to
          </v-icon>
        </a>
      </v-toolbar-title>
  
      <v-spacer></v-spacer>
  
      <!-- Botão para abrir o menu hambúrguer -->
      <v-btn icon @click="toggleDrawer" aria-label="Abrir menu">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
  
      <!-- Menu lateral -->
      <v-navigation-drawer v-model="drawer" app temporary color="#252525">
        <v-list dense>
          <v-list-item to="/" class="nav-button" aria-label="Ir para a home">
            <v-list-item-icon><v-icon>mdi-home</v-icon></v-list-item-icon>
            <v-list-item-content>Home</v-list-item-content>
          </v-list-item>
          <v-list-item to="/resumo" class="nav-button" aria-label="Ir para o resumo">
            <v-list-item-icon><v-icon>mdi-file-account</v-icon></v-list-item-icon>
            <v-list-item-content>Resume</v-list-item-content>
          </v-list-item>
          <v-list-item to="/Projetos" class="nav-button" aria-label="Ir para os projetos">
            <v-list-item-icon><v-icon>mdi-folder-network-outline</v-icon></v-list-item-icon>
            <v-list-item-content>Projects</v-list-item-content>
          </v-list-item>
          <v-list-item to="/contato" class="nav-button" aria-label="Ir para o contato">
            <v-list-item-icon><v-icon>mdi-contacts</v-icon></v-list-item-icon>
            <v-list-item-content>Contact</v-list-item-content>
          </v-list-item>
        </v-list>
      </v-navigation-drawer>
    </v-app-bar>
  </template>
  
  <script>
  export default {
    name: 'AppbarMobile',
    data() {
      return {
        drawer: false, // Controle do menu
      };
    },
    methods: {
      toggleDrawer() {
        this.drawer = !this.drawer;
      }
    }
  };
  </script>
  
  <style scoped>
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&display=swap');
  
  a {
    text-decoration: none;
  }
  
  .logo-text {
    color: #FFEA00;
    font-family: 'Merriweather', serif;
    font-size: 32px;
    font-weight: 700;
    letter-spacing: 1px;
  }
  
  .nav-button {
    color: #f7f7f7;
    border-bottom: 1px solid #FFEA00;
    background-color: transparent;
    padding: 10px;
  }
  
  .nav-button:hover {
    background-color: #312d018e;
    box-shadow: 0 2px 15px #FFEA00;
  }
  </style>
  