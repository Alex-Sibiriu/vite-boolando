<script>
  export default {
    data() {
      return {
        footerMenu: [
          {
            title: 'Informazioni legali',
            link: '#'
          },
          {
            title: 'Informativa sulla privacy',
            link: '#'
          },
          {
            title: 'Diritto di recesso',
            link: '#'
          }
        ],
        socials: [
          {
            icon: 'fa-brands fa-square-twitter',
            link: '#'
          },
          {
            icon: 'fa-brands fa-square-facebook',
            link: '#'
          },
          {
            icon: 'fa-brands fa-square-instagram',
            link: '#'
          },
          {
            icon: 'fa-brands fa-square-pinterest',
            link: '#'
          },
          {
            icon: 'fa-brands fa-square-youtube',
            link: '#'
          }
        ]
      }
    },
  }
</script>

<template>

  <footer>
    <div class="container d-flex">
      <!-- INFO SECTION -->
      <div class="info-section">
        <h2>Boolando s.r.l.</h2>
        <ul class="d-flex">
          <li
            v-for="(section, index) in footerMenu"
            :key="index">
            <a :href="section.link">{{ section.title }}</a>
          </li>
        </ul>
      </div>
      <!-- /INFO SECTION -->

      <!-- SOCIAL -->
      <div class="socials">
        <h4>Trovaci anche su</h4>
        <ul class="social-icons d-flex">
          <li
            v-for="(social, index) in socials"
            :key="index">
            <a :href="social.link">
              <i :class="social.icon"></i>
            </a>
          </li>
        </ul>
      </div>
      <!-- /SOCIAL -->
    </div>
  </footer>

</template>

<style lang="scss" scoped>
  @import '../assets/scss/partials/general';
  @import '../assets/scss/partials/variables';
  @import '../assets/scss/partials/utilities';

  footer {
    background-color: $footer-clr;
    height: $footer-h;
    // margin-top: 15px;
    .container {
      padding: 0 10px;
      justify-content: space-between;
      .info-section {
        margin-top: 33px;
        h2 {
          color: $primary-clr;
          font-size: 1.15rem;
          margin-bottom: 10px;
        }
        li {
          font-size: .9rem;
          margin-right: 10px;
        }
      }
      .socials {
        margin-top: 33px;
        width: 150px;
        h4 {
          margin-bottom: 10px;
          font-size: .9rem;
          padding-left: 5px;
        }
        .social-icons {
          font-size: 1.32rem;
          justify-content: space-around;
        }
      }
    }
  }
</style>