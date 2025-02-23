
<template>
    <v-btn
      color="bgColor3"
      @click="scrollToTop()"
      icon
      :class="{ hidden: !isVisible }"
    >
      <v-icon icon="mdi-arrow-up" color="#f7f7f7" background-color="#252525"></v-icon>
    </v-btn>
  </template>
  
  <script>
  export default {
  name: "ScrollTop",
  data: () => ({
  isVisible: false,
  
  }),
  
  mounted() {
   this.showBtn();
  },
  
  methods: {
  showBtn() {
    setTimeout(()=>
        this.isVisible = true, 2000
    )
  },
  
  scrollToTop() {
    window.scrollTo({
      top: 0,
      behavior: "smooth",
    });
  },
  },
  };
  </script>
  <style scoped>
  .v-btn {
  z-index: 999;
  position: fixed;
  bottom: 2%;
  right: 2%;
  transition: 2s all;
  transform: scale(1);
  box-shadow: 0 2px 15px rgba(219, 187, 4, 0.5);
  border: 1px solid gold;
  }
  .v-btn:hover{
    background-color: gold;
  }
  
  .hidden {
  box-shadow: none;
  transform: scale(0);
  }
  </style>
  