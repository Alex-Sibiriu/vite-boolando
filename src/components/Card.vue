<script>
  export default {
    // props: {
    //   product: Object
    // }
  }
</script>

<template>

  <!-- Card 1 -->
  <div class="card">
    <!-- Card Top -->
    <div class="card-top">
      <a href="#">
        <img src="../../public/assets/img/1.webp" alt="item 1" class="first-img">
        <img src="../../public/assets/img/1b.webp" alt="item 1b" class="hover-img">
      </a>
      <div class="heart">&hearts;</div>
      <div class="item-characteristics d-flex">
        <span class="discount">-50%</span>
        <span class="sustainability">Sostenibilità</span>
      </div>
    </div>
    <!-- /Card Top -->

    <!-- Card Bottom -->
    <div class="card-bottom">
      <div>
        <a href="#" class="brand">Levi's</a>
      </div>
      <div class="item-name">
        <a href="#">
          <h3>Relaxed fit tee unisex</h3>
        </a>
      </div>
      <div class="prices">
        <span class="current-price">14,99 &euro; </span>
        <span class="original-price">29,99 &euro;</span>
      </div>
    </div>
    <!-- /Card Bottom -->
  </div>
  <!-- /Card 1 -->

</template>

<style lang="scss" scoped>
  @import '../assets/scss/partials/general';
  @import '../assets/scss/partials/variables';
  @import '../assets/scss/partials/utilities';

  .card {
  width: 465px;
  min-width: 250px;
  margin: 10px 10px 40px;
  .card-top {
    position: relative;
    &:hover .hover-img {
      z-index: 2;
    }
    img {
      width: 100%;
      &.hover-img {
        position: absolute;
        top: 0;
        left: 0;
        z-index: -1;
      }
    }
    .heart {
      width: 53px;
      line-height: 53px;
      text-align: center;
      color: black;
      font-size: 2.3rem;
      background-color: white;
      cursor: pointer;
    
      position: absolute;
      top: 10px;
      right: 0;
      z-index: 3;
    }
    .item-characteristics {
      color: white;
      font-size: .87rem;
      font-weight: bold;
      position: absolute;
      left: 0;
      bottom: 48px;
      z-index: 3;
      .discount {
        background-color: red;
        margin-right: 4px;
        padding: 6px 11px;
      }
      .sustainability {
        background-color: #008000;
        padding: 6px 11px;
      }
    }
  }
  .card-bottom {
    .brand, .prices {
      color: #71716F;
      font-size: .87rem;
      font-weight: bold;
    }
    .prices {
      font-size: .93rem;
      .current-price {
        color: red;
      }
      .original-price {
        text-decoration: line-through ;
      }
    }

  }
}

.card-top .heart:hover {
  color: red;
}
  
</style>