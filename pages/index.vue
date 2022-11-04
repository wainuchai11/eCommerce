<template>
  <div>
    <Nav />
    <home-carousel :sale_items="sale_item" />
    <br />
    <v-container>
      <h1 class="text-md-h4 text-h6">Check these out</h1>
      <br />
      <ProductSlider :products="products" />
    </v-container>
    <Footer />
  </div>
</template>

<script>
import Footer from "../components/Footer.vue";
import HomeCarousel from "../components/HomeCarousel.vue";
import Nav from "../components/Nav.vue";
import ProductSlider from "../components/ProductSlider.vue";

export default {
  async created() {
    this.sale_item = await this.$content("products")
      .where({ onSale: true })
      .fetch();
    this.products = await this.$content("products").fetch();
  },
  data() {
    return {
      products: null,
      sale_item: null,
    };
  },
  components: { Nav, HomeCarousel, Footer, Nav, Footer, ProductSlider },
};
</script>

<style>
</style>