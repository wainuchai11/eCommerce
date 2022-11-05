<template>
  <div>
    <!-- <Nav /> -->
    <home-carousel :sale_items="sale_item" />
    <br />
    <v-container>
      <h1 class="text-md-h4 text-h6">Check these out</h1>
      <br />
      <ProductSlider :products="products" />
      <br />
      <br />
      <br />
      <Newsletter />
    </v-container>
    <!-- <Footer />
    <SrcollTop /> -->
  </div>
</template>

<script>
import Footer from "../components/Footer.vue";
import HomeCarousel from "../components/HomeCarousel.vue";
import Nav from "../components/Nav.vue";
import Newsletter from "../components/Newsletter.vue";
import ProductSlider from "../components/ProductSlider.vue";
import SrcollTop from "../components/SrcollTop.vue";
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
  components: {
    Nav,
    HomeCarousel,
    Footer,
    Nav,
    Footer,
    ProductSlider,
    Newsletter,
    SrcollTop,
    SrcollTop,
  },
};
</script>

<style>
</style>