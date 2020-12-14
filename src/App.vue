<template>
  <div id="app">
    <Header />
    <Hero />
    <Shorten  
      @termChange="onTermChange" 
      :urls="urls" 
      :error="error"
      :loading="loading"/>
    <Statistics />
    <Action />
    <Footer />
  </div>
</template>

<script>
import axios from 'axios';
import Header from './components/Header.vue';
import Hero from './components/Hero.vue';
import Shorten from './components/Shorten.vue';
import Statistics from './components/Statistics.vue';
import Action from './components/Action.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Header,
    Hero,
    Shorten,
    Statistics,
    Action,
    Footer
  },
  data() {
    return {
      urls: [],
      loading: false,
      error: false
    };
  },
  methods: {

    async onTermChange(urlString) {
      console.log('url string' ,urlString)
      this.loading = true;
      this.error = false;
       await axios
        .get(`https://api.shrtco.de/v2/shorten?url=${urlString}`)
        .then((response) => {
         console.log(response.data)
         this.urls.push(response.data.result)
         this.loading = false
        })
        .catch(error => {
          console.log('error', error);
          this.error  = true;
          this.loading = false;
        })
      
      
    },
  },
};
</script>

<style lang="scss">
//reset
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  outline: 0;
  box-sizing: border-box;
}

img {
  width: 100%;
}
ul {
  list-style-type: none;
}

a {
  text-decoration: none;
}

// color variables
$darkBlue: hsl(233, 26%, 24%);
$limeGreen: hsl(136, 65%, 51%);
$brightCyan: hsl(192, 70%, 51%);
$grayishBlue: hsl(233, 8%, 62%);
$lightGrayishBlue: hsl(220, 16%, 96%);
$veryLightGray: hsl(0, 0%, 98%);
$white: hsl(0, 0%, 100%);

//mixins
@mixin respond($breakpoint) {
  @if $breakpoint == big-desktop {
    @media (min-width: 1800px) {
      @content;
    }
  }
  @if $breakpoint == desktop {
    @media (min-width: 1400px) {
      @content;
    }
  }
  @if $breakpoint == tab-land {
    @media (min-width: 1200px) {
      @content;
    }
  }
  @if $breakpoint == tab-port {
    @media (min-width: 900px) {
      @content;
    }
  }
  @if $breakpoint == phone {
    @media (min-width: 600px) {
      @content;
    }
  }
}

html {
  font-size: 62.5%; //1rem = 10px
  @include respond(phone) {
    font-size: 50%; //1rem = 8px
  }
  @include respond(tab-land) {
    font-size: 50%; //1rem = 8px
  }
  @include respond(tab-port) {
    font-size: 56.25%; //1rem = 9px
  }
  @include respond(big-desktop) {
    font-size: 75%; //1rem = 12px
  }
}

.container {
  width: 80%;
  margin: 0 auto;
  overflow-x: hidden;
}
</style>
