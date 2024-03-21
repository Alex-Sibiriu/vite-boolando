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
        iconsMenu: [
          {
            icon: 'fa-regular fa-user',
            link: '#'
          },
          {
            icon: 'fa-regular fa-heart',
            link: '#'
          },
          {
            icon: 'fa-solid fa-bag-shopping',
            link: '#'
          }
        ]
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
          <li
            v-for="(section, index) in iconsMenu"
            :key="index"><a :href="section.link">
              <i :class="section.icon"></i></a>
          </li>
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
    height: header-h;
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