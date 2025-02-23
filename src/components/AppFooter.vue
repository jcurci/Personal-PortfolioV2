<template>
  <footer class="footer" align="center">
    <v-col cols="12" md="12">
      <div class="media-btn" align="center">
        <v-btn href="https://br.linkedin.com/in/jhocurci" target="_blank">
          <v-icon>mdi-linkedin</v-icon>
        </v-btn>  
        <v-btn href="https://br.linkedin.com/in/jhocurci" target="_blank">
          <v-icon>mdi-github</v-icon>
        </v-btn>  
        <v-btn to="/contato">
          <v-icon >mdi-email</v-icon>
        </v-btn>  
      </div>
    </v-col>
    <v-container>
      <v-row cols="12">
        <v-col cols="12">
          <p class="tittle">Personal Web Portfolio - © 2024</p> 
        </v-col>
      </v-row>
    </v-container>
  </footer>
</template>
<script>
export default {
  name: 'Footer'
}
</script>

<style scoped>

.footer {
  font-family: 'Merriweather', sans-serif;
  text-align: center;
}

p {
  color: #f7f7f7;
  font-size: 12px;
}
.v-btn{
  margin: 4px;
  border-radius: 10px;
}
.v-btn:hover{
  box-shadow: 0 2px 15px #FFEA00;
  transform: translateY(-3px);
}


</style>
