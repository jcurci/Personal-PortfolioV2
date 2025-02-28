<template>
  <v-app-bar app floating color="#252525" elevation="24">
    <v-toolbar-title>
      <a href="/" class="logo-text">
        Curci
        <v-icon class="mr-2 neon-icon" size="45" aria-hidden="true">
          mdi-dev-to
        </v-icon>
      </a>
    </v-toolbar-title>

    <v-spacer></v-spacer>

    <v-btn icon @click="toggleDrawer">
      <v-icon>mdi-menu</v-icon>
    </v-btn>
  </v-app-bar>

  <v-navigation-drawer v-model="drawer" app temporary location="right" color="#252525">

    <v-list dense>
      <v-list-item to="/" class="nav-button">
        <v-icon>mdi-home</v-icon>
        <v-list-item-title>Home</v-list-item-title>
      </v-list-item>

      <v-list-item to="/resumo" class="nav-button">
        <v-icon>mdi-file-account</v-icon>
        <v-list-item-title>Resume</v-list-item-title>
      </v-list-item>

      <v-list-item to="/Projetos" class="nav-button">
        <v-icon>mdi-folder-network-outline</v-icon>
        <v-list-item-title>Projects</v-list-item-title>
      </v-list-item>

      <v-list-item to="/contato" class="nav-button">
        <v-icon>mdi-contacts</v-icon>
        <v-list-item-title>Contact</v-list-item-title>
      </v-list-item>

    </v-list>
  </v-navigation-drawer>
</template>

<script>
import { ref } from 'vue';

export default {
  name: 'AppbarMobile',
  setup() {
    const drawer = ref(false);

    const toggleDrawer = () => {
      drawer.value = !drawer.value;
    };

    return { drawer, toggleDrawer };
  },
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
