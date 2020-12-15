<template>
  <section class="statistics">
    <div >
    <h2>Advanced Statistics</h2>
    <p class="statistics-sub">
      Track how your links are performing across the web with our advanced
      statistics dashboard.
    </p>
    </div>
    <div class="boxes">
      <div class="box">
        <div class="image-circle">
          <img src="../../images/icon-brand-recognition.svg">
        </div>
        
        <p class="box-title">Brand Recognition</p>
        <p class="box-text">Boost your brand recognition with each click. Generic links
          don’t mean a thing. Branded links help instil confidence in your content.</p>
      </div>

      <div class="box">
        <div class="image-circle">
          <img src="../../images/icon-detailed-records.svg">
        </div>
        <p class="box-title">Detailed Records</p>
        <p class="box-text">Gain insights into who is clicking your links. Knowing when
    and where people engage with your content helps inform better decisions.</p>
      </div>

       <div class="box">
        <div class="image-circle">
          <img src="../../images/icon-fully-customizable.svg">
        </div>
        <p class="box-title">Fully Customizable</p>
        <p class="box-text" >Improve brand awareness and content discoverability
    through customizable links, supercharging audience engagement.</p>
      </div>

    </div>
  </section>
</template>

<script>
export default {
  name: "Statistics",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.statistics {
 background-color: #f0f1f6;
 padding-top: 6.5rem;
 text-align: center;

 @include respond(tab-port) {
     padding-bottom: 7rem;
     padding-top: 8rem;
  }
}

.statistics h2 {
  font-size: 3rem;
  margin-bottom: 2rem;

  @include respond(tab-port) {
    font-size: 4.5rem;
  }
}

.statistics-sub {
  margin-bottom: 8rem;
  font-size: 2rem;
  color: $gray;

   @include respond(tab-port) {
    width: 50%;
    margin: auto;
     margin-bottom: 21rem;
  }
}

.boxes {
  @include respond(tab-port) {
    display: flex;
    width: 80%;
    margin: auto;
  }
}

.box {
  background-color: white;
  width: 90%;
  margin: auto;
  margin-bottom: 8rem;
  padding: 2rem;
  border-radius: 5px;
  position: relative;

  @include respond(tab-port) {
    margin-right: 3rem;
    margin-top: -10rem;
    margin-bottom: 18rem;

    &:nth-child(2) {
      margin-top: -6rem;
      margin-bottom: 14rem;
    }
    &:nth-child(3) {
      margin-top: -4rem;
      margin-bottom: 10rem;
    }
  }
}

.box:not(:last-child)::after {
  content:""; 
    background:$cyan; 
    position: absolute; 
    bottom: -8rem; 
    left: 50%; 
    height: 8rem; 
    width: 6px;

    @include respond(tab-port) {
    bottom: 14rem;
    left: 100%; 
    height: 6px; 
    width: 5rem;
  }
}

.box-title {
  font-size: 2.4rem;
  font-weight: 700;
  margin-bottom: 2rem;

}

.box-text {
  font-size: 1.6rem;
  color: $gray;
  margin-bottom: 2.5rem;
}

.image-circle {
  padding: 29px 10px;
  background-color: $veryDarkViolet;
  border-radius: 50%;
  // width: 30%;
  width: 100px;
  margin: auto;
  margin-top: -6rem;
  margin-bottom: 3rem;

   @include respond(tab-port) {
      width: 110px;
   }

  &:nth-child(1) {
    @include respond(tab-port) {
      margin-left: 2rem;
    }
    }
}

.image-circle img {
   width: 35px;
   @include respond(tab-port) {
      width: 45px;
   }
}

</style>