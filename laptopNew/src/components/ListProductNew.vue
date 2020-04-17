<template>
  <div id="comp-listNew">
    <div class="title-new">
      <div class="img-new"></div
      >SẢN PHẨM MỚI RA
    </div>
    <div class="content-new">
    <Product
              v-for="(n,key) in numbers"
              v-bind:key="key"/>
    </div>
    <div class="background-btn">
      <button class="btn-add-all">Xem tất cả</button>
    </div>
  </div>
</template>

<script>
import Product from './Product'
export default {
  name: 'comp-listNew',
  data () {
    return {
      numbers: [ 1, 2, 3, 4, 5 ]
    }
  },
  components: {
    Product
  }
}
</script>

<style>
#comp-listNew {
  height: auto;
  background-color: #ffffff;
  margin-bottom: 50px;
}
.img-new {
  width: 40px;
  height: 40px;
  background-size: contain;
  background-repeat: no-repeat;
  background-image: url('../assets/icon/new.png');
  margin-right: 10px;
}
.title-new {
  display: flex;
  width: 100%;
  height: 50px;
  background-color: white;
  color: orange;
  align-items: center;
  padding-left: 25px;
  font-weight: 600;
  font-size: 22px;
  border-bottom: 1px solid orange;
}
.content-new {
  display: flex;
  justify-content: space-around;
}
.background-btn {
  width: 100%;
  text-align: center;
}
.btn-add-all {
  margin-top: 25px;
  margin-bottom: 50px;
  padding: 7px 50px;
  background-color: #ffffff;
  color: orange;
  border: 1px solid orange;
  border-radius: 1px;

}
.btn-add-all:hover {
  background-color: orange;
  color: white;
}
.btn-add-all:focus {
  outline: none;
}
</style>
