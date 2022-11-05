<template>
  <v-app>
    <v-main
      dark
      :style="{ backgroundColor: $vuetify.theme.dark ? '#0a0514' : 'white' }"
    >
      <Nav />
      <Nuxt />
      <Footer></Footer>
      <srcoll-top></srcoll-top>
    </v-main>
  </v-app>
</template>

<script>
import Footer from "../components/Footer.vue";
import Nav from "../components/Nav.vue";
import SrcollTop from '../components/SrcollTop.vue';

export default {
  name: "DefaultLayout",
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      items: [
        {
          icon: "mdi-apps",
          title: "Welcome",
          to: "/",
        },
        {
          icon: "mdi-chart-bubble",
          title: "Inspire",
          to: "/inspire",
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "Vuetify.js",
    };
  },
  components: { Nav, Footer, SrcollTop },
};
</script>
