<template>
  <div id="menu-product"
      v-on:mouseover="mouseoverRange(idProduct, $event)"
      v-on:mouseleave="mouseleaveRange(idProduct, $event)"
          >
    <ul>
      <li class="li-type"
          v-on:mouseover="mouseover(key,isCheckDetail, $event)"
          v-on:mouseleave="mouseleave(key,isCheckDetail, $event)"
          v-for="(typeP,key) in listProduct"
      v-bind:key="key">{{typeP.typeProduct}}
      <div class="li-after"></div>
      </li>
    </ul>
    <div id="menu-content" class="menu-content"
    v-on:mouseover="mouseoverDetail(idProduct,isCheckDetail, $event)"
              v-on:mouseleave="mouseleaveDetail(idProduct,isCheckDetail, $event)">
      <ul>
          <li v-for="(type,id) in listProduct[idProduct].arrTypeProduct"
              v-bind:key="id"
              >{{type.name}} |
            <ul class="branch">
              <li v-for="(branch,index) in type.arrType"
                  v-bind:key="index">{{branch}}
              </li>
            </ul>
          </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'menu-product',
  data () {
    return {
      idProduct: 0,
      isCheckMenu: false,
      isCheckRange: false,
      isCheckDetail: false
    }
  },
  props: {
    listProduct: {
      type: Array,
    }
  },
  methods: {
    mouseover(id,check, event){
      this.idProduct = id;
      event.target.style.backgroundColor = "orange";
      event.target.style.color = "white";
      document.getElementById('menu-content').style.visibility = "visible";
      document.getElementsByClassName("li-type")[id].style.backgroundColor = "orange";
      document.getElementsByClassName("li-type")[id].style.color = "white";
      document.getElementsByClassName("li-after")[id].style.visibility = "visible";
      document.getElementsByClassName("li-after")[id].style.backgroundColor = "transparent";
      check = true;
    },
    mouseleave(id,check, event){
      event.target.style.backgroundColor = "white";
      event.target.style.color = "#333";
      document.getElementsByClassName("li-after")[id].style.visibility = "hidden";
    },
    mouseoverDetail(id, check, event){
      check = true;
      document.getElementsByClassName("li-type")[id].style.backgroundColor = "orange";
      document.getElementsByClassName("li-type")[id].style.color = "white";
      document.getElementsByClassName("li-after")[id].style.visibility = "visible";
      document.getElementsByClassName("li-after")[id].style.backgroundColor = "transparent";

    },
    mouseleaveDetail(id, check,  event){
        check = false;
      document.getElementsByClassName("li-type")[id].style.backgroundColor = "white";
      document.getElementsByClassName("li-type")[id].style.color = "#333";
      document.getElementsByClassName("li-after")[id].style.visibility = "hidden";
      document.getElementsByClassName("li-after")[id].style.backgroundColor = "transparent";
    },
    mouseoverRange(id, event){
      this.isCheckRange = true;

    },
    mouseleaveRange(id, event){
      this.isCheckRange = false;
      document.getElementById('menu-content').style.visibility = "hidden";
      document.getElementsByClassName("li-after")[id].style.visibility = "hidden";
      document.getElementsByClassName("li-type")[id].style.backgroundColor = "white";
      document.getElementsByClassName("li-type")[id].style.color = "#333";
    }
  }

}
</script>

<style>
#menu-product {
  padding: 0;
  width: 92%;
  height: auto;
  margin-left: 0;
  background-color: transparent;
}
#menu-product >ul {
  list-style-type: none;
}
#menu-product ul li {
  background-color: #ffffff;
  width: 150px;
  padding: 7px 10px;
  font-size: 13px;
  font-weight: 600;
}
#menu-product >ul >li:hover {
  position: relative;
  width: 150px;
  z-index: 99;
  cursor: pointer;
}
#menu-product >ul >li:hover .table-menu {
  display: block;
  text-align: center;
  justify-content: center;
}
.li-after {
  visibility: hidden;
  content:'';
  float: right;
  width: 0;
  height: 0;
  position: relative;
  top: -7px;
  left: 31px;
  border-top: 16px solid transparent;
  border-left: 20px solid orange;
  border-bottom: 17px solid transparent;
  z-index: 99;
}

.menu-content {
    visibility:hidden;
    height: 320px;
    width: 79% !important;
    background-color: white;
    position: absolute;
    top: 139px;
    left: 194px;
    z-index: 50;
    border-radius: 2px !important;
    border-radius: 5px;
    width: 270px;

}
.menu-content ul {
  list-style: none;
}
.menu-content >ul >li {
  cursor: pointer;
    color: orange;
    padding: 5px;
    margin-left: -40px;
    font-size: 14px !important;
    font-weight: 400 !important;
    width: 200px !important;
    text-align: end;
    background-color: transparent !important;
}
.table-menu >li:hover{
    cursor: pointer;
}
.branch {
  display: flex;
  position: relative;
  top:-25px;
  left:150px;
  list-style: none;
  color: rgb(128, 128, 128);
  background-color: transparent !important;
  margin-bottom: -10px;
}
.branch > li {
  background-color: transparent !important;
  font-size: 12px !important;
  font-weight: 300 !important;
  width: 200px !important;
  text-align: start;
  white-space: nowrap;
}
.branch >li:hover {
    color: black;
    cursor: pointer;
}
</style>
