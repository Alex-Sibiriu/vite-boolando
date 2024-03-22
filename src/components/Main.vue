<script>
  import Card from './Card.vue';

  export default {
    components: {
      Card,
    }
  }
</script>

<template>
  <main>
    <div class="container d-flex">
      <Card />
    </div>
  </main>
</template>

<style lang="scss" scoped>
  @import '../assets/scss/partials/general';
  @import '../assets/scss/partials/variables';
  @import '../assets/scss/partials/utilities';

  main {
    height: calc(100vh - $footer-h); // Provvisorio
    padding-top: 123px;
  }
</style>