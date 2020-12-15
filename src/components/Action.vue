<template>
  <section >
    <div class="action">
    <p>Boost your links today</p>
    <button>Get Started</button>
    </div>
  </section>
</template>

<script>
export default {
  name: "Action"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.action {
  width: 100%;
  margin: auto;
  padding: 7rem 2rem;
  text-align: center;
   background: url(../../images/bg-boost-mobile.svg) no-repeat center center;
    background-size: cover;
    background-color: #3a3053;

  @include respond(tab-port) {
     background: url(../../images/bg-boost-desktop.svg) no-repeat center center;
    background-size: cover;
    background-color: #3a3053;
  }
  
}

.action p {
  font-size: 3rem;
  color: white;
  margin-bottom: 1.5rem;
  @include respond(tab-port) {
     font-size: 4.2rem;
  }
}

.action button {
  background-color: $cyan;
  color: white;
  font-size: 2rem;
  display: block;
  padding: 1.5rem 4rem;
  border-radius: 100px;
  margin: auto;
  border: none;
  transition: 0.3s;

  &:hover {
    background-color: #85f0f0;
  }
}
</style>