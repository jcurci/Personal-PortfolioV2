<template>
    <v-app-bar
      app
      color="#252525"
      elevation = "24"
    >
      <v-toolbar-title>
        <a href="/" class="logo-text">Curci
          <v-icon
            class="mr-2 neon-icon"
            size="45"
          >
            mdi-dev-to
          </v-icon>
        </a>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn 
        to="/" 
        class="nav-button" 
      >
        <v-icon left>mdi-home</v-icon>
        Home
      </v-btn>
      <v-btn 
        to="/resumo" 
        class="nav-button" 
      >
        <v-icon left>mdi-file-account</v-icon>
        Resume
      </v-btn>
      <v-btn 
        to="/Projetos" 
        class="nav-button" 
      >
        <v-icon left>mdi-folder-network-outline</v-icon>
        Projects
      </v-btn>
      <v-btn 
        to="/contato" 
        class="nav-button" 
      >
        <v-icon left>mdi-contacts</v-icon>
        Contact
      </v-btn>
    </v-app-bar>
  </template>
  
  <script>
  export default {
    name: 'Appbar',
  }
  </script>
  
  <style>
  @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&display=swap');
  
  
  a{
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
    border: 1.5px solid #FFEA00; 
    border-radius: 10px;
    background-color: #252525;
    margin-left: 10px; 
    transition: all 0.3s ease; 
  }
  
  .nav-button:hover {
    border-color: #FFEA00; 
    transform: translateY(-3px);
    background-color: #312d018e;
    box-shadow: 0 2px 15px #FFEA00;
  }
  
  .v-icon {
    color: #FFEA00; 
  }
  </style>
  