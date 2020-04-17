<template>
  <div id="app">
    <Header/>
    <div class="menu-banner">
      <MenuProduct v-bind:listProduct="listProduct"
      v-bind:arrLaptop="arrLaptop"/>
      <slider v-scroll="handleScrollSlide"></slider>
    </div>
    <div class="body-content" id="body-content">
      <ListProductNew/>
      <ListProductRec/>
      <ListProductSale/>
    </div>
    <Footer/>
  </div>
</template>

<script>
import Header from './components/Header'
import MenuProduct from './components/MenuProduct'
import Slider from './components/Slider'
import ListProductNew from './components/ListProductNew'
import ListProductRec from './components/ListProductRec'
import ListProductSale from './components/ListProductSale'
import Footer from './components/Footer'
export default {
  name: 'app',
  data () {
    return {
      listProduct :[
        {id: 0,typeProduct:'Laptop' ,
        arrTypeProduct:[
          {name:'Laptop theo thương hiệu',arrType: [
        'Acer','Apple','ASUS','DELL','HP','Lenovo','MSI'
        ]},
          {name:'Laptop theo giá',arrType: [
        'Dưới 10 triệu','10 - 15 triệu','15 - 20 triệu','25 - 30 triệu','Trên 30 triệu'
        ]},
          {name:'Laptop theo Chip xử lý',arrType: [
        'Intel Core i3','Intel Core i5','Intel Core i7','Intel Core i9','AMD Ryzen 3','AMD Ryzen 5','AMD Ryzen 7'
        ]},
          {name:'Laptop theo kích thước',arrType: [
        'Dưới 13 inch','13 - 15 inch','Trên 15 inch'
        ]},
          {name:'Laptop theo card đồ họa',arrType: [
        'GTX 1050','GTX 1050Ti','GTX 1650','GTX 1660Ti','RTX Series'
        ]}
        ]},
        {id : 1,typeProduct:'Linh kiện'},
        {id : 2,typeProduct:'Màn hình'},
        {id : 3,typeProduct:'Bàn phím'},
        {id : 4,typeProduct:'Chuột'},
        {id : 5,typeProduct:'Đồ lót chuột'},
        {id : 6,typeProduct:'Tai nghe'},
        {id : 7,typeProduct:'Loa nghe nhạc',arrTypeProduct:[
          {name:'Laptop theo thương hiệu',arrType: [
        'Acer','Apple','ASUS','DELL','HP','Lenovo','MSI'
        ]},
          {name:'Laptop theo giá',arrType: [
        'Dưới 10 triệu','10 - 15 triệu','15 - 20 triệu','25 - 30 triệu','Trên 30 triệu'
        ]},
          {name:'Laptop theo Chip xử lý',arrType: [
        'Intel Core i3','Intel Core i5','Intel Core i7','Intel Core i9','AMD Ryzen 3','AMD Ryzen 5','AMD Ryzen 7'
        ]},
          {name:'Laptop theo kích thước',arrType: [
        'Dưới 13 inch','13 - 15 inch','Trên 15 inch'
        ]},
          {name:'Laptop theo card đồ họa',arrType: [
        'GTX 1050','GTX 1050Ti','GTX 1650','GTX 1660Ti','RTX Series'
        ]}
        ]}
      ]
    }
  },
  components:{
    Header,
    MenuProduct,
    Slider,
    ListProductNew,
    ListProductRec,
    ListProductSale,
    Footer
  },
  methods: {
    handleScrollSlide(e){
      var navbar = document.getElementById("body-content");
      var sticky = navbar.offsetTop - 140;
      console.log(sticky);
      if (window.pageYOffset > sticky) {
        document.getElementById("nav-icon").style.display = "block";
        document.getElementById("btn-logo").style.fontSize = "22px";
      } else {
        document.getElementById("nav-icon").style.display = "none";
        document.getElementById("btn-logo").style.fontSize = "30px";
      }
    }
  }
}

</script>

<style>
body{
  margin: 0;
  background-color: #f1f0f1;
}
#app {
  font-family: Roboto,sans-serif !important;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 0;
  padding: 0;
}
.menu-banner {
  width: 100%;
  display: flex;
  margin-top: 5px;
}
.body-content {
  width: 96%;
  height: auto;
  background-color: transparent;
  margin-left: 2%;
  position: relative;
  top: 80px;
}
</style>
