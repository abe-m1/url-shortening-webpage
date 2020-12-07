<template>
  <section >
    <div class="footer">
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
  padding: 6rem 2rem;
  text-align: center;
}

.footer p {
  font-size: 2rem;
  color: white;
  margin-bottom: 2rem;
}

.action button {
  width: 100%;
  padding: 2rem;
  border-radius: 10px;
  background-color: $cyan;
  color: white;
}
</style>