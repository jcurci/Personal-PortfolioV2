<template>
  <v-app>
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
import { ref, onMounted, onBeforeUnmount } from 'vue';
import AppbarMobile from '@/components/AppBarMobile.vue';
import Appbar from '@/components/Appbar.vue';

export default {
  components: {
    AppbarMobile,
    Appbar
  },
  setup() {
    const isMobile = ref(window.innerWidth <= 768);

    const checkScreenSize = () => {
      isMobile.value = window.innerWidth <= 768;
    };

    onMounted(() => {
      window.addEventListener('resize', checkScreenSize);
    });

    onBeforeUnmount(() => {
      window.removeEventListener('resize', checkScreenSize);
    });

    return { isMobile };
  }
};
</script>
