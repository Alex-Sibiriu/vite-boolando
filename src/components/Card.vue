<script>
  export default {
    props: {
      item: Object
    },
    methods: {
      toggleFavorite() {
        this.item.isInFavorites = !this.item.isInFavorites
      },

      isDiscounted(dress) {
        return dress.badges.find(badge => badge.type === 'discount') !== undefined;
      },

      discountedPrice(dress) {
        if (this.isDiscounted(dress)) {
          const discountBadge = dress.badges.find(badge => badge.type === 'discount');
          const discountValue = parseInt(discountBadge.value.replace('%', ''));
          const discountedPrice = dress.price + (dress.price / 100 * discountValue);
          return discountedPrice.toFixed(2);
        } else {
          return dress.price
        }
      }
    },
  }
</script>

<template>

  <!-- Card 1 -->
  <div class="card">
    <!-- Card Top -->
    <div class="card-top">
      <a href="#">
        <img :src="`/assets/img/${item.frontImage}`" :alt="item.name" class="first-img">
        <img :src="`/assets/img/${item.backImage}`" :alt="item.name" class="hover-img">
      </a>
      <div class="heart"
        :class="{'active' : item.isInFavorites}"
        @mouseover.stop=""
        @click="toggleFavorite"
        >&hearts;</div>
      <div class="item-characteristics d-flex">
        <span
          v-for="(badge, index) in item.badges"
          :key="index"
          :class="badge.type">{{badge.value}}</span>
      </div>
    </div>
    <!-- /Card Top -->

    <!-- Card Bottom -->
    <div class="card-bottom">
      <div>
        <a href="#" class="brand">{{ item.brand }}</a>
      </div>
      <div class="item-name">
        <a href="#">
          <h3>{{ item.name }}</h3>
        </a>
      </div>
      <div class="prices">
        <span class="current-price">{{ discountedPrice(item) }} &euro; </span>
        <span v-if="isDiscounted(item)" class="original-price">{{ item.price }} &euro;</span>
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
      color: $secondary-clr;
      font-size: 2.3rem;
      background-color: $primary-clr;
      cursor: pointer;
    
      position: absolute;
      top: 10px;
      right: 0;
      z-index: 3;
      &.active {
        color: $active-clr;
      }
    }
    .item-characteristics {
      color: $primary-clr;
      font-size: .87rem;
      font-weight: bold;
      position: absolute;
      left: 0;
      bottom: 48px;
      z-index: 3;
      .discount {
        background-color: $active-clr;
        padding: 6px 11px;
      }
      .tag {
        background-color: $sustainability-clr;
        margin-right: 4px;
        padding: 6px 11px;
      }
    }
  }
  .card-bottom {
    .brand, .prices {
      color: $tertiary-clr;
      font-size: .87rem;
      font-weight: bold;
    }
    .prices {
      font-size: .93rem;
      .current-price {
        color: $active-clr
      }
      .original-price {
        text-decoration: line-through ;
      }
    }

  }
}
  
</style>