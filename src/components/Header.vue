<script>

  export default {
    data() {
      return {
        sections: [
          {
            title: 'Donna',
            link: '#'
          },
          {
            title: 'Uomo',
            link: '#'
          },
          {
            title: 'Bambini',
            link: '#'
          }
        ],
      }
    },
  }
</script>

<template>

  <header>
    <div class="container d-flex">
      <nav class="categories">
        <ul class="d-flex">
          <li
            v-for="(section, index) in sections"
            :key="index"><a
            :href="section.link">{{ section.title }}</a></li>
        </ul>
      </nav>

      <div>
        <img src="/assets/img/boolean-logo.png" alt="logo">
      </div>

      <nav class="profile">
        <ul class="d-flex">
          <li><a href="#"><i class="fa-regular fa-user"></i></a></li>
          <li><a href="#"><i class="fa-regular fa-heart"></i></a></li>
          <li><a href="#"><i class="fa-solid fa-bag-shopping"></i></a></li>
        </ul>
      </nav>
    </div>
  </header>

</template>

<style lang="scss" scoped>
  @import '../assets/scss/partials/general';
  @import '../assets/scss/partials/variables';
  @import '../assets/scss/partials/utilities';

  header {
    width: 100%;
    height: 73px;
    line-height: 73px;
    font-size: 1.05rem;
    font-weight: bold;
    color: $primary-clr;
    background-color: $header-clr;
    margin-bottom: 53px;
    box-shadow: 0px 0px 5px $secondary-clr;
    position: fixed;
    z-index: 10;
    .container {
      justify-content: space-between;
      padding: 0 10px;
      .categories {
        width: 15%;
        ul {
          justify-content: flex-start;
          li {
            margin-right: 10px;
          }
        }
      }
      img {
        height: 32px;
        vertical-align: middle;
      }
      .profile {
        width: 15%;
        ul {
          justify-content: flex-end;
          li {
            margin-left: 10px;
          }
        }
      }
    }
  }
</style>