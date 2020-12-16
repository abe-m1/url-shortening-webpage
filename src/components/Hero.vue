<template>
  <section class="hero">
    <div class="image-container">
      <img src="../../images/illustration-working.svg" alt="hero-image"/>
    </div>
    <div class="text-container">
       <h2>More than just shorter links</h2>
      <p>
      Build your brand’s recognition and get detailed insights on how your links
      are performing.
    </p>
    <div>
       <button>Get Started</button>
    </div>
   
    </div>
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
  overflow-x: hidden;

  @include respond(tab-port) {
      display: flex;
      margin-bottom: 12rem;
  }
}
.hero img {
  margin-bottom: 3rem;
  width: 92%;
  @include respond(tab-port) {
    width: 100%;
  }
 
}

.image-container {

   margin-right: -16rem;
  
  @include respond(tab-port) {
      order: 1;
      flex: 47%;
    }
}

.text-container {  
  display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;

  @include respond(tab-port) {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: flex-start;
      padding-left: 12rem;
      flex: 53%;
    }
}

.hero h2 {
  font-size: 4rem;
  text-align: center;
  margin-bottom: 2rem;
  line-height: 1.3;

  @include respond(tab-port) {
    font-size: 9rem;
    text-align: left;
    margin-bottom: 0;
  }
}

.hero p {
  font-size: 1.8rem;
  text-align: center;
  margin-bottom: 2.3rem;
  color: $gray;
  width: 80%;

  @include respond(tab-port) {
    font-size: 2.3rem;
    text-align: left;
    width: 80%;
  }
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
  transition: 0.3s;

  &:hover {
    opacity: 0.5;
  }
}
</style>