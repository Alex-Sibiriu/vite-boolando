<script>
  import Card from './Card.vue';
  import {products} from '../assets/data/products.json'

  export default {
    components: {
      Card,
    },
    data() {
      return {
        products
      }
    },
  }
</script>

<template>
  <main>
    <div class="container d-flex">
      <Card 
        v-for="product in this.products"
        :key="product.id"
        :item="product"
      />
    </div>
  </main>
</template>

<style lang="scss" scoped>
  @import '../assets/scss/partials/general';
  @import '../assets/scss/partials/variables';
  @import '../assets/scss/partials/utilities';

  main {
    padding-top: 123px;
  }
</style>