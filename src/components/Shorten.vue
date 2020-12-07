<template>
  <section >
    <div class="shorten">
    <input />
    <button>Shorten It!</button>
    </div>
  </section>
</template>

<script>
export default {
  name: "Shorten",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.shorten {
  background-color: $veryDarkViolet;
  width: 90%;
  margin: auto;
  padding: 2rem;
  border-radius: 5px;
  z-index: 5;
}

.shorten input {
  width: 100%;
  margin-bottom: 1rem;
  padding: 2rem;
}

.shorten button {
  width: 100%;
  padding: 2rem;
  border-radius: 10px;
  background-color: $cyan;
  color: white;
}
</style>