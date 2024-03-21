<script>
  export default {
    
  }
</script>

<template>

  <footer>
    <div class="container d-flex">
      <!-- INFO SECTION -->
      <div class="info-section">
        <h2>Boolando s.r.l.</h2>
        <ul class="d-flex">
          <li><a href="#">Informazioni legali</a></li>
          <li><a href="#">Informativa sulla privacy</a></li>
          <li><a href="#">Diritto di recesso</a></li>
        </ul>
      </div>
      <!-- /INFO SECTION -->

      <!-- SOCIAL -->
      <div class="socials">
        <h4>Trovaci anche su</h4>
        <ul class="social-icons d-flex">
          <li><a href="#"><i class="fa-brands fa-square-twitter"></i></a></li>
          <li><a href="#"><i class="fa-brands fa-square-facebook"></i></a></li>
          <li><a href="#"><i class="fa-brands fa-square-instagram"></i></a></li>
          <li><a href="#"><i class="fa-brands fa-square-pinterest"></i></a></li>
          <li><a href="#"><i class="fa-brands fa-square-youtube"></i></a></li>
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