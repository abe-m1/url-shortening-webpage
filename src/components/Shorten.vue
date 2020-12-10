<template>
  <section class="shorten-container">
    <div class="shorten">
    <input type="text" @input="onInput"/>
    <div class="error" v-if="this.error">ERROR</div>
    <button v-if="this.loading === false" @click="onClick">Shorten It!</button>
    <button v-else ><div class="loader"></div></button>
    
    </div>
    
    <ul>
      <ShortenedItem
        v-for="url in urls"
        :url="url"
        :key="url.short_link"></ShortenedItem>
  </ul>
  </section>
</template>

<script>
import ShortenedItem from './ShortenedItem';
export default {
  name: "Shorten",
  props: ['urls', 'loading', 'error'],
  components: {
    ShortenedItem,
  },
  data() {
    return {
      textInput: '',
      hasError: false
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
      this.textInput = '';
      this.loading = true;
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

.shorten-container {
  background-color: #f0f1f6;
}
.shorten {
  background-color: $veryDarkViolet;
  width: 90%;
  margin: auto;
  padding: 2rem;
  border-radius: 5px;
  z-index: 5;
  margin-bottom: 2rem;
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

.loader {
  margin: auto;
  border: 4px solid #f3f3f3; /* Light grey */
  border-top: 4px solid #3498db; /* Blue */
  border-radius: 50%;
  width: 20px;
  height: 20px;
  animation: spin 2s linear infinite;
}

@keyframes spin {
  0% { transform: rotate(0deg); }
  100% { transform: rotate(360deg); }
}

.error {
  color: red;
}
</style>