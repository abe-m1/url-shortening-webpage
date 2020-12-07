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
  background-color: #3a3053;
  width: 100%;
  margin: auto;
  padding: 6rem 2rem;
  text-align: center;
}

.action p {
  font-size: 3rem;
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