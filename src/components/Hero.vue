<template>
  <section class="hero">
    <img src="../../images/illustration-working.svg" />
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
  margin-bottom: 5rem;
}
.hero img {
  margin-bottom: 3rem;
}

.hero h2 {
  font-size: 3rem;
  text-align: center;
  margin-bottom: 2rem;
}

.hero p {
  font-size: 2.5rem;
  text-align: center;
  margin-bottom: 2rem;
}

.hero button {
  display: block;
  padding: 2rem 4rem;
  border-radius: 100px;
  background-color: $cyan;
  color: white;
  margin: auto;
  border: none;
}
</style>