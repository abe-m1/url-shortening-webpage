<template>
  <section class="hero container">
    <div class="image-container">
      <img src="../../images/illustration-working.svg" />
    </div>
    <h2>More than just shorter links</h2>
    <p>
      Build your brand’s recognition and get detailed insights on how your links
      are performing.
    </p>
    <button>Get Started</button>
  </section>
</template>

<script>
export default {
  name: "Hero",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.hero {
  margin-bottom: 10rem;
}
.hero img {
  margin-bottom: 3rem;
 
}

.image-container {
  // width: 100%;
   margin-right: -16rem;
}

.hero h2 {
  font-size: 4rem;
  text-align: center;
  margin-bottom: 2rem;
  line-height: 1.3;
}

.hero p {
  font-size: 1.8rem;
  text-align: center;
  margin-bottom: 2.3rem;
  color: $gray;
}

.hero button {
  font-size: 2rem;
  display: block;
  padding: 1.5rem 5rem;
  border-radius: 100px;
  background-color: $cyan;
  color: white;
  margin: auto;
  border: none;
}
</style>