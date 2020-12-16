<template>
  <div class="container">
    <header class="header">
      <img class="header__logo" src="../../images/logo.svg" alt="logo" />
      <ul class="header__menu">
        <li class="header__menu__menu-item">Features</li>
        <li class="header__menu__menu-item">Pricing</li>
        <li class="header__menu__menu-item">Resources</li>
      </ul>
      <ul class="header__button">
        <button class="button-gradient header-button-clear">Login</button>
        <button class="header-button">Sign Up</button> 
      </ul>
     
      <div class="hamburger" @click="onClick">
        <div class="hamburgerTop"></div>
        <div class="hamburgerMiddle"></div>
        <div class="hamburgerBottom"></div>
      </div>
    </header>

     <div class="nav-container" 
     :class="[
      openNav ? 'show' : '',
    ]">
      <div class="nav-modal">
        <ul class="ham-list">
          <li class="ham-item">Features</li>
          <li class="ham-item">Pricing</li>
          <li class="ham-item">Resources</li>
          <hr class="nav-ruler">
          <li class="ham-item">Login</li>
          <button class="ham-button">Sign Up</button>
        </ul>
      </div>
    </div>
  </div>

  
</template>

<script>
export default {
  name: 'Header',
  props: {
    msg: String,
  },
  data() {
    return {
      openNav: false
    }
  },
  methods: {
    onClick: function(){
      console.log('click ham', this.openNav)
      this.openNav = !this.openNav;
      console.log(this.openNav)
    }
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">

.header {
  padding: 2rem 0;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;

  @include respond(tab-port) {
    width: 100%;
    margin: auto;
    padding: 3rem 0;
  }

  &__logo {
    width: 13rem;

     @include respond(tab-port) {
      margin-right: 4rem;
    }
  }

  &__button {
    
    display: none;

    @include respond(tab-port) {
      display: block;
    }
  }

  &__menu {
    font-size: 1.9rem;
    display: none;

    @include respond(tab-port) {
      display: flex;
      margin-right: auto;
    }

    &__menu-item {
      @include respond(tab-port) {
        align-self: stretch;
      }

      list-style: none;
      padding-bottom: 3rem;
      padding-top: 3rem;
      border: 3px solid transparent;

      &:not(:last-child) {
        margin-right: 4rem;
      }

      @include respond(tab-port) {
        font-size: 1.6rem;
        display: flex;
        align-items: center;
        color: $grayishViolet;

        &:not(:last-child) {
          margin-right: 3rem;
        }

        &:hover {
          color: black;
        }
      }
      @include respond(tab-land) {
        &:not(:last-child) {
          margin-right: 6rem;
        }
      }
    }
  }
}

.header-button-clear {
  color: black;
  padding: 2rem 3rem;
  border: none;
  background-color: transparent;
  border-radius: 100px;
  font-size: 1.6rem;
}

.header-button {
  background-color: $cyan;
  color: white;
  padding: 1.2rem 3rem;
  border: none;
  border-radius: 100px;
  transition: 0.3s;
  font-size: 1.6rem;

  &:hover {
    opacity: 0.5;
  }
}

.hamburger {
  width: 30px;
  height: 30px;
  margin: 20px;

  @include respond(tab-port) {
   display:none;
  }
}

.hamburgerTop, .hamburgerMiddle, .hamburgerBottom {
  position: absolute;
  display: block;
  width: 30px;
  height: 3px;
  background: $gray;
}

.hamburgerTop, .hamburgerBottom {
  transition: transform 0.4s ease, margin-top 0.3s ease 0.4s;
}

.hamburgerMiddle {
  transition: opacity 0.2s ease 0.5s;
}

.hamburgerTop {
  margin-top: 7px;
}

.hamburgerMiddle {
  margin-top: 15px;
}

.hamburgerBottom {
  margin-top: 23px;
}

.hamburgerTop.open, .hamburgerBottom.open {
  transition: margin-top 0.3s ease, transform 0.4s ease 0.3s;
}

.hamburgerTop.open {
  transform: rotate(45deg);
  margin-top: 15px;
}

.hamburgerMiddle.open {
  opacity: 0;
  transition: none;
}

.hamburgerBottom.open {
  transform: rotate(-45deg);
  margin-top: 15px;
}

.nav-container {
  display: none
}

.show {
  display: block
}

.nav-container {
  color: white;
  position: absolute;
  top: 12%;
  width: 80%;
  left: 10%;
  border-radius: 1rem;
  text-align: center;
  box-shadow: 0px 3px 15px rgba(0, 0, 0, 0.2);
  padding: 2.7rem 3rem 3.7rem 3rem;
  background-color: $veryDarkBlue;
  z-index: 1010;
}

.ham-item {
  font-size: 2rem;
  margin-bottom: 2rem;
  list-style: none;
}

.nav-ruler {
  border: 1px solid $gray;
  margin-bottom: 2rem;
}

.ham-button {
  font-size: 2rem;
  width: 100%;
  display: block;
  padding: 1.5rem 8rem;
  border-radius: 100px;
  background-color: $cyan;
  color: white;
  margin: auto;
  border: none;
}

</style>
