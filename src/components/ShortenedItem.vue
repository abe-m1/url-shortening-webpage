<template>
  <li class="item-container">
    <p class="original-link">{{url.original_link}}</p>
    <hr >
      <p class="short-link">{{url.short_link}}</p> 
      <button v-if="this.copied === false" @click="onClick" class="button copy-button">Copy</button>
      <button v-else class="button copied-button">Copied!</button>
  </li>
</template>

<script>
export default {
  name: 'ShortenedItem',
  props: ['url'],
  data() {
    return {
      copied: false
    }
  },
  methods: {
    onClick: function(){
      this.copied = true;
    }
}
};
</script>

<style scoped lang="scss">
.item-container {
  width: 90%;
  margin: auto;
  padding: 2rem;
  background-color: white;
  border-radius: 10px;

   @include respond(tab-port) {
    display: flex;
    justify-content: space-between;
    align-items: center;
   }

  &:not(:last-of-type){
    margin-bottom: 2rem;
  }
}

.button {
  width: 100%;
   font-size: 2rem;
  display: block;
  padding: 1.5rem 5rem;
  border-radius: 10px;
  margin: auto;
  border: none;
  color: white;

   @include respond(tab-port) {
    width: auto;
    margin: 0;
   }

   &:not(:last-of-type){
    margin-bottom: 2rem;
  }
}
.copy-button {
  background-color: $cyan; 
  transition: 0.3s;

  &:hover {
    opacity: 0.5;
  }

   @include respond(tab-port) {
   margin-left: 2rem;
   
   }
}

.copied-button {
  background-color: blue;
   @include respond(tab-port) {
   margin-left: 2rem;
   
   }
}

hr {
  margin-bottom: 1rem;
}

.original-link {
  margin-bottom: 1rem;
  font-size: 1.6rem;
}

.short-link {
  color: $cyan;
  margin-bottom: 2rem;
  font-size: 1.6rem;

   @include respond(tab-port) {
   margin-left: auto;

   }
}
</style>