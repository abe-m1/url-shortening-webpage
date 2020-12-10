<template>
  <section >
    <div class="shorten">
    <input type="text" @input="onInput"/>
    <button @click="onClick">Shorten It!</button>
    </div>
    <ul>
    <li
      v-for="url in urls"
      :url="url"
      :key="url.short_link"> {{url.short_link}}</li>
  </ul>
  </section>
</template>

<script>
export default {
  name: "Shorten",
  props: ['urls'],
  data() {
    return {
      textInput: ''
    }
  },
  methods: {
    onInput: function(event) {
      console.log(event.target.value)
      this.textInput = event.target.value
    },
    onClick: function(){
      console.log('click')
      this.$emit('termChange', this.textInput);
    }
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
  border-radius: 10px;
}

.shorten button {
  width: 100%;
  padding: 1.5rem;
  border-radius: 10px;
  background-color: $cyan;
  color: white;
  font-size: 2rem;
}
</style>