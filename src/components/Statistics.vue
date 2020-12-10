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
          <img src="../../images/icon-detailed-records.svg">
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
          <img src="../../images/icon-detailed-records.svg">
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
 padding-top: 8rem;
 padding-bottom: 2rem;
 text-align: center;
}

.statistics h2 {
  font-size: 3rem;
  margin-bottom: 2rem;
}

.statistics-sub {
  margin-bottom: 8rem;
  font-size: 1.8rem;
  color: $gray;
}

.box {
  background-color: white;
  width: 90%;
  margin: auto;
  margin-bottom: 8rem;
  padding: 2rem;
  border-radius: 5px;
  position: relative;
}

.box:not(:last-child)::after {
  content:""; 
    background:$cyan; 
    position: absolute; 
    bottom: -5rem; 
    left: 50%; 
    height: 5rem; 
    width: 6px;
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
  padding: 1.4rem 1.8rem;
  background-color: $veryDarkViolet;
  border-radius: 150px;
  width: 30%;
  margin: auto;
  margin-top: -6rem;
  margin-bottom: 3rem;
}

</style>