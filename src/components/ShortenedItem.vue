<template>
  <li class="item-container">
    <p class="original-link">{{url.original_link}}</p>
    <hr>
      <p class="short-link">{{url.short_link}}</p> 
      <button class="copy-button">Copy</button>
  </li>
</template>

<script>
export default {
  name: 'ShortenedItem',
  props: ['url'],
};
</script>

<style scoped lang="scss">
.item-container {
  width: 90%;
  margin: auto;
  padding: 2rem;
  background-color: white;
  border-radius: 10px;

  &:not(:last-of-type){
    margin-bottom: 2rem;
  }
}

.copy-button {
  width: 100%;
   font-size: 2rem;
  display: block;
  padding: 1.5rem 5rem;
  border-radius: 10px;
  background-color: $cyan;
  color: white;
  margin: auto;
  border: none;
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
}
</style>