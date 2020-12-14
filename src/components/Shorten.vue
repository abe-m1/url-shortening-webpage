<template>
  <section class="shorten-container">
    <form @submit.prevent="onClick" class="shorten">
      <div class="input-container">
         <input 
          :class="hasError && 'input-error'" 
          placeholder="Shorten a link here..."
          type="text" @input="onInput"/>
          <span class="error" v-if="this.error || this.hasError">{{ this.errorMessage || 'Error'}}</span>
      </div>
      <div class="button-container">
         <button v-if="this.loading === false">Shorten It!</button>
         <button v-else ><div class="loader"></div></button>
      </div> 
    </form>
    
    <ul class="results-container">
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
      hasError: false,
      errorMessage: ''
    }
  },
  
  methods: {
    onInput: function(event) {
      console.log(event.target.value)
      this.textInput = event.target.value
    },
    onClick: function(e){
      e.preventDefault()
      if (!this.textInput){
        console.log(this.textInput)
        this.hasError = true;
        this.errorMessage = "Please add a link";
        return;
      }
      console.log('click')
      this.$emit('termChange', this.textInput);
      this.textInput = '';
      this.loading = true;
      this.hasError = false;
      this.errorMessage = '';

      e.target.reset();
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
  width: 90%;
  margin: 0 auto;
  padding: 2rem;
  border-radius: 5px;
  z-index: 5;
  background: url(../../images/bg-shorten-mobile.svg) no-repeat center center;
  background-size: contain;
  background-color: $veryDarkViolet;

  @include respond(tab-port) {
    display: flex;
    justify-content: flex-start;
    width: 80%;
    padding: 5rem;
    position: relative;
    top: -5rem;
    background: url(../../images/bg-shorten-desktop.svg) no-repeat center center;
    background-size: contain;
    background-color: $veryDarkViolet;
  }
}

.shorten input {
  width: 100%;
  margin-bottom: 1rem;
  padding: 2rem;
  border-radius: 10px;
  border: none;

  @include respond(tab-port) {
    margin-right: 1rem;
  }
}

.shorten button {
  width: 100%;
  padding: 1.5rem;
  border-radius: 10px;
  background-color: $cyan;
  color: white;
  font-size: 2rem;
  border: none;
  transition: 0.3s;

  &:hover {
    background-color: #85f0f0;
  }
}

.input-container {
  flex: 70%;
  @include respond(tab-port) {
  margin-right: 2rem;
  }
}

.button-container {
  flex: 30%;

}

.results-container {
   @include respond(tab-port) {
    width: 90%;
    margin: auto;
   }
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

.input-error {
  border: 2px solid red;
}
</style>