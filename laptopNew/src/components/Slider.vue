<template>
<div id="slide" >
  <div id="carouselExampleIndicators" class="carousel slide" data-ride="carousel">
    <ol class="carousel-indicators">
      <li data-target="#carouselExampleIndicators" data-slide-to="0" class="active"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="1"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="2"></li>
      <li data-target="#carouselExampleIndicators" data-slide-to="3"></li>
    </ol>
    <div class="carousel-inner">
      <div class="carousel-item active">
        <img class="d-block w-100" src="../assets/banner/banner6.jpg" alt="First slide">
      </div>
      <div class="carousel-item">
        <img class="d-block w-100" src="../assets/banner/banner5.jpg" alt="Second slide">
      </div>
      <div class="carousel-item">
        <img class="d-block w-100" src="../assets/banner/banner7.png" alt="Third slide">
      </div>
      <div class="carousel-item">
        <img class="d-block w-100" src="../assets/banner/banner8.png" alt="Four slide">
      </div>
    </div>
    <a class="carousel-control-prev" href="#carouselExampleIndicators" role="button" data-slide="prev">
      <span class="carousel-control-prev-icon" aria-hidden="true"></span>
      <span class="sr-only">Previous</span>
    </a>
    <a class="carousel-control-next" href="#carouselExampleIndicators" role="button" data-slide="next">
      <span class="carousel-control-next-icon" aria-hidden="true"></span>
      <span class="sr-only">Next</span>
    </a>
  </div>
  <div class="list-img">
    <img class="img-item" src="../assets/banner/banner9.png">
    <img class="img-item" src="../assets/banner/banner10.png">
    <img class="img-item" src="../assets/banner/banner11.png">
  </div>
</div>
</template>

<script>
export default {
  name: 'slide',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
};

</script>

<style>
#slide {
  margin: 0;
  padding: 0;
  height: 310px;
  width: 750px;
  display: flex;
  position: absolute;
  right: 22%;
}
.carousel-inner {
  border-radius: 2px;
}
.carousel-item img {
  margin: 0;
  padding: 0;
  background-size: contain;
  background-repeat: no-repeat;
  height: 310px;
  width: 750px !important;
}
.img-item {
  height: 100px;
  width: 200px;
  margin: 0 5px 5px 5px;
  border-radius: 2px;
}
</style>
