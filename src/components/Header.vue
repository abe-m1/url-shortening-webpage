<template>
  <div>
    <header class="header">
      <img class="header__logo" src="../../images/logo.svg" alt="" />
      <ul class="header__menu">
        <li class="header__menu__menu-item">Features</li>
        <li class="header__menu__menu-item">Pricing</li>
        <li class="header__menu__menu-item">Resources</li>
      </ul>
      <!-- <button class="button-gradient header-button">Login</button> -->
      <!-- <button class="button-gradient header-button">Sign Up</button> -->
      <div class="hamburger">
        <div class="hamburgerTop"></div>
        <div class="hamburgerMiddle"></div>
        <div class="hamburgerBottom"></div>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: 'Header',
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
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

.header {
  padding: 4rem 2rem;
  width: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;

  @include respond(tab-port) {
    width: 80%;
    margin: auto;
    padding: 0;
  }

  &__logo {
    width: 15rem;
  }

  &__menu {
    font-size: 1.9rem;
    display: none;

    @include respond(tab-port) {
      display: flex;
    }

    &__menu-item {
      @include respond(tab-port) {
        align-self: stretch;
      }

      list-style: none;
      padding-bottom: 3rem;
      color: $primary;
      padding-top: 3rem;
      border: 3px solid transparent;

      &:hover {
        border-style: solid;
        color: blue;
        border-width: 3px;
        border-image: linear-gradient(to left, green, orange) 0 0 100% 0/0 0 4px
          0;
      }

      &:not(:last-child) {
        margin-right: 4rem;
      }

      @include respond(tab-port) {
        font-size: 1.4rem;
        display: flex;
        align-items: center;

        &:not(:last-child) {
          margin-right: 3rem;
        }
      }
      @include respond(tab-land) {
        &:not(:last-child) {
          margin-right: 6rem;
        }
      }
    }

    // &__button {
    // font-size: 1.9rem;
    // display: none;

    // @include respond(tab-port) {
    //   display: flex;
    // }
  }
}

/* Main style of the hamburger icon */
.hamburger {
  width: 30px;
  height: 30px;
  margin: 20px;
}

/* Style of the layers of the hamburger */
.hamburgerTop, .hamburgerMiddle, .hamburgerBottom {
  position: absolute;
  display: block;
  width: 30px;
  height: 3px;
  background: black;
}

/* Animation from open (X) to close (hamburger) */
.hamburgerTop, .hamburgerBottom {
  /*
   * Parameter explanation:
   * transform    - rotating back elements
   * 0.4s         - duration of 'transform'-animation
   * ease         - animation style for 'transform'
   *
   * margin-top   - bring layers to original position
   * 0.3s         - duration for 'margin-top'
   * ease         - animation style for 'margin-top'
   * 0.4s         - wait 0.4s (duration of 'transform') before starting 'margin-top'-animation
   */
  transition: transform 0.4s ease, margin-top 0.3s ease 0.4s;
}

.hamburgerMiddle {
  transition: opacity 0.2s ease 0.5s;
}

/* Margin between the layers */
.hamburgerTop {
  margin-top: 7px;
}

.hamburgerMiddle {
  margin-top: 15px;
}

.hamburgerBottom {
  margin-top: 23px;
}

/* Animation from close (hamburger) to open (X) */
.hamburgerTop.open, .hamburgerBottom.open {
  transition: margin-top 0.3s ease, transform 0.4s ease 0.3s;
}

/* 
 * All layers at same position.
 * One layer not visible at all.
 * Two layers forming an 'X'-shape.
 */
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

</style>
