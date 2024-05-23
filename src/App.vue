<template>
  <div id="app">
    <Navbar />
    <Carousel />

    <div class="product-container">
      <ProductCard
        v-for="product in products"
        :key="product.id"
        :product="product"
        @add-to-cart="handleAddToCart"
      />
    </div>

    <Footer />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Carousel from './components/Carousel.vue';
import ProductCard from './components/ProductCard.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    Carousel,
    ProductCard,
    Footer
  },
  data() {
    return {
      products: [
        { id: 1, name: 'Lipstick', price: 'Rp612.580', imgSrc: 'https://wallpapercave.com/wp/wp3225604.jpg  ' },
        { id: 2, name: 'Highheels', price: 'Rp200.000', imgSrc: 'https://wallpapercave.com/dwp2x/wp3843346.jpg' },
        { id: 3, name: 'HandBag', price: 'Rp300.000', imgSrc: 'https://wallpapercave.com/dwp2x/wp8146701.jpg' }
      ]
    };
  },
  methods: {
    handleAddToCart(product) {
      // Implementasikan logika untuk menambahkan produk ke keranjang
      console.log('Tambah ke keranjang:', product);
    }
  }
}
</script>

<style>
body {
  background-color: #f8f9fa;
  margin: 0;
  font-family: Arial, sans-serif;
}

.product-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  padding: 20px;
}
</style>
