<template>
  <section >
    <div class="footer container">
       <img class="footer-logo" src="../../images/logo-white.svg" alt="" />
    <p class="footer-title">Features</p>
    <p class="footer-item">Link Shortening</p>
    <p class="footer-item">Branded Links</p>
    <p class="footer-item">Analytics</p>

    <p class="footer-title">Resources</p>
    <p class="footer-item">Blog</p>
    <p class="footer-item">Developers</p>
    <p class="footer-item">Support</p>

    <p class="footer-title">Company</p>
    <p class="footer-item">About</p>
    <p class="footer-item">Our Team</p>
    <p class="footer-item">Careers</p>
    <p class="footer-item">Contact</p>

     <div class="social">
      <ion-icon name="logo-facebook"></ion-icon>
      <ion-icon name="logo-twitter"></ion-icon>
      <ion-icon name="logo-pinterest"></ion-icon>
      <ion-icon name="logo-instagram"></ion-icon>
            </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "Footer"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.footer {
  background-color: #232027;
  width: 100%;
  margin: auto;
  padding: 5rem 2rem;
  text-align: center;
}

.footer-logo {
  width: 13rem;
}

.footer-title {
  font-size: 1.7rem;
  color: white;
  margin-top: 4rem;
  margin-bottom: 2rem;
}

.footer-item {
  font-size: 1.4rem;
  color: $gray;
  margin-bottom: 1.3rem;
}

.action button {
  width: 100%;
  padding: 2rem;
  border-radius: 10px;
  background-color: $cyan;
  color: white;
}

ion-icon {
  font-size: 35px;
  color: #fff;
  margin-left: 1.5rem;

  // &:not(:last-of-type) {
  //   margin-left: 1.5rem;
  // }

  // &:hover {
  //   color: $limeGreen;
  // }

  // @include respond(tab-port) {
  //   font-size: 30px;
  // }
}

.social {
  margin-top: 4rem;
}
</style>