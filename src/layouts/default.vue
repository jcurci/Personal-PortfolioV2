<template>
  <v-app>
    <!-- Exibir a versão correta da AppBar -->
    <AppbarMobile v-if="isMobile" />
    <Appbar v-else />
    
    <ScrollTop />
    <v-main>
      <router-view />
    </v-main>
    <AppFooter />
  </v-app>
</template>

<script>
import Appbar from '@/components/Appbar.vue';
import AppbarMobile from '@/components/AppBarMobile.vue';
import ScrollTop from '@/components/ScrollTop.vue';
import AppFooter from '@/components/AppFooter.vue';

export default {
  components: {
    Appbar,
    AppbarMobile,
    ScrollTop,
    AppFooter
  },
  data() {
    return {
      isMobile: false
    };
  },
  mounted() {
    this.checkScreenSize();
    window.addEventListener('resize', this.checkScreenSize);
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.checkScreenSize);
  },
  methods: {
    checkScreenSize() {
      this.isMobile = window.innerWidth <= 600; // Define o breakpoint para o mobile
    }
  }
};
</script>
