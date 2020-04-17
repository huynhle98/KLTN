<template>
  <header id="comp-header">
    <section class="banner" id="banner">
        <div class="banner-content">
        </div>
    </section>
    <div class="navbar" id="navbar" v-scroll="handleScroll">
      <div class="logo">
        <input class="menu-btn" type="checkbox" id="menu-btn">
        <label class="menu-icon" for="menu-btn"><span id="nav-icon" class="nav-icon"></span></label>
        <a class="btn-logo" id="btn-logo">Laptop</a>
      </div>
      <div class="form-search">
        <input class="inp-search" placeholder="Tìm kiếm sản phẩm"/>
        <button class="btn-search">
          <div></div>
        </button>
      </div>
      <div class="gr-btn-nav">
      <button class="btn-news">
        <div></div>
        <label>Khuyến mãi</label>
      </button>
      <button class="btn-sign" v-on:click="turnOnTab(1)">
        <div></div>
        <label>Đăng nhập</label>
      </button>
      <button class="btn-cart">
        <div></div>
        <label>Giỏ hàng </label>
        <label class="cart-number"> {{cartNumber}} </label>
      </button>
      </div>
    </div>
    <div class="content"></div>
    <TabSignInUp>
      <div class="tabs-content" v-if="BtnSignActive === 1">
      <div class="tab-header">
        <ul class="tab-sign-inup" >
          <li
            v-for="(tab,index) in tabsSign"
            v-bind:key="index"
            v-on:click="setTabSign(index)"
            v-bind:class="{ active: tabSignActive === index }">
            {{tab.text}}
          </li>
        </ul>
        <div class="close-background">
            <button class="login-close" v-on:click="turnOnTab(0)"></button>
        </div>
      </div>
      <div class="sign-in" v-if="tabSignActive === 0">
        <div class="login-main">
          <div class="login-left">
            <label>Đăng nhập để nhận nhiều ưu đãi hấp dẫn</label>
              <div></div>
          </div>
            <form class="login-content" action="#" method="post">
                    <input class="login-item" placeholder="Email hoặc số điện thoại">
                    <input class="login-item" type="password" placeholder="Mật khẩu">
                    <a class="login-item-forget" href="#">Quên mật khẩu?</a>
                    <button class="login-item" type="button">Đăng nhập</button>
                    <label>Hoặc</label>
                    <button class="login-item-fb" type="button">Đăng nhập bằng Facebook</button>
                    <button class="login-item-gg" type="button">Đăng nhập bằng Gmail</button>
            </form>
        </div>
      </div>
      <div class="sign-up" v-else>
        <div class="login-main">
          <div class="login-left">
            <label>Đăng ký để mua hàng dễ dàng, quản lý tài khoản của bạn</label>
              <div></div>
          </div>
            <form class="login-content" action="#" method="post">
                    <input class="login-item" placeholder="Họ tên">
                    <input class="login-item" placeholder="Số điện thoại">
                    <input class="login-item" placeholder="Tên tài khoản">
                    <input class="login-item" placeholder="Mật khẩu">
                    <input class="login-item" placeholder="Nhập lại mật khẩu">
                    <div>
                    <label>Giới tính</label>
                    <select class="select-sex">
                      <option>Chọn giới tính</option>
                      <option>Nam</option>
                      <option>Nữ</option>
                    </select>
                    </div>
                    <button class="login-item" type="button">Tạo tài khoản</button>
            </form>
        </div>
      </div>
      </div>

    </TabSignInUp>
  </header>
</template>

<script>
import TabSignInUp from './TabSignInUp'
export default {
 name: 'comp-header',
  data () {
    return {
      tabsSign: [
        { text: 'Đăng nhập'},
        { text: 'Đăng ký'}
      ],
      tabSignActive: 0,
      BtnSignActive: 0,
      cartNumber: 0
    }
  },
  methods: {
    setTabSign(index) {
      this.tabSignActive = index;
    },
    turnOnTab(isClick) {
      this.BtnSignActive = isClick;
      if(isClick === 1){
        var divOver = document.createElement('div');
        divOver.id="over";
        document.body.appendChild(divOver);
      }
      else{
        document.getElementById('over').remove();
      }
    },
    handleScroll(e){
      var navbar = document.getElementById("navbar");
      var sticky = navbar.offsetTop;
      console.log(sticky);
      if (window.pageYOffset > sticky) {
        navbar.classList.add("sticky")
      } else {
        navbar.classList.remove("sticky");
      }
    }
  },
  computed: {

  },
  components: {
    TabSignInUp
  },
}
</script>

<style>
#comp-header {
  margin: 0;
  padding: 0;
  font-size: 15px;

}
.banner {
    width: 100%;
    height: 50px;
    background-size: contain;
    transition: all .1s ease-in-out;
    background-image: url('../assets/banner/banner1.jpg');
    animation:  banner 28s infinite linear;
}
.banner-content {
    margin: 0;
    padding: 0;
    width: 100%;
    height: 100%;
    color: #ffffff;

    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
@keyframes banner {
    0%{
        background-image: url('../assets/banner/banner1.jpg');
    }
    25%{
        background-image: url('../assets/banner/banner1.jpg');
    }
    27%{
        background-image: url('../assets/banner/banner2.jpg');
    }
    50%{
        background-image: url('../assets/banner/banner2.jpg');
    }
    52%{
        background-image: url('../assets/banner/banner3.jpg');
    }
    75%{
        background-image: url('../assets/banner/banner3.jpg');
    }
    77%{
        background-image: url('../assets/banner/banner4.jpg');
    }
    99%{
        background-image: url('../assets/banner/banner4.jpg');
    }
}
.logo {
  display: flex;
  align-items: center;
  width: 150px;
}
.menu-btn {
    display: none;
}
.menu-btn:checked ~ .menu {
    max-height: 200px;
}
.menu-btn:checked ~ .menu-icon .nav-icon {
    background: transparent;
}
.menu-btn:checked ~ .menu-icon .nav-icon::before {
    transform: rotate(-45deg);
    top: 0;
    background: red;
}
.menu-btn:checked ~ .menu-icon .nav-icon::after {
    transform: rotate(45deg);
    top: 0;
    background: red;
}
.menu-icon {
    padding: 23px 15px;
    position: relative;
    float: right;

}
.menu-icon .nav-icon {
    background:  #333;
    display: none;
    height: 2px;
    width: 25px;
    position: relative;
    top: 5px;
    transition: background .2s ease-out;

}
.menu-icon .nav-icon::before {
    background: #333;
    content: "";
    display: block;
    height: 100%;
    width: 100%;
    position: absolute;
    transition: all .2s ease-out;
    top: 9px;
}
.menu-icon .nav-icon::after {
    background: #333;
    content: "";
    display: block;
    height: 100%;
    width: 100%;
    position: absolute;
    transition: all .2s ease-out;
    top: -9px;
}
.navbar {
  overflow: hidden;
  display:flex;
  justify-content: space-around;
  align-items: center;
  background-color: #ffffff;
  padding: 15px 0;
  z-index: 999;
}
.sticky {
  position: fixed;
  top: 0;
  width: 100%;
}
.sticky + .content {
  padding-top: 60px;
}
.btn-logo {
  color: orange !important;
  background: transparent;
  border: none;
  font-size: 30px;
  font-weight: 600;
}
.btn-logo:hover {
  cursor: pointer;;
}
.btn-logo:focus {
  outline: none;
}
.form-search {
  display: inline-flex;
}
.inp-search {
  padding: 7px 10px;
  width: 350px;
  border: 1px solid #a9a9a9;
  border-radius: 2px 0 0 2px;
}
.btn-search {
  display: flex;
  width: 50px;
  background: transparent;
  background-position: center;
  border: 1px solid #a9a9a9;
  border-left: none;
  justify-content: center;
  border-radius: 0 2px 2px 0;
}
.btn-search div {
  width: 15px;
  height: 15px;
  background-image: url('../assets/icon/search.png');
  background-size: contain;
  background-repeat: no-repeat;
}
.btn-search:hover {
  cursor: pointer;
  background-color: #f0f0f0;
}
.gr-btn-nav {
  display: flex;
  align-items: center;
}
.btn-news {
  padding: 5px;
  display: flex;
  align-items: center;
  background: transparent;
  border: 1px solid orange;
  color: orange;
  border-radius: 2px;
  margin-right: 20px;
}
.btn-news:hover {
  cursor: pointer;
}
.btn-news:focus {
  outline: none;
}
.btn-news div {
  width: 30px;
  height: 30px;
  background-image: url('../assets/icon/coupon.png');
  background-size: contain;
  background-repeat: no-repeat;
  margin-right : 10px;
}
.btn-news label {
  position: relative;
  top: 4px;
}
.btn-news label:hover {
  cursor: pointer;
}
.btn-sign {
  padding: 5px;
  display: flex;
  align-items: center;
  background: transparent;
  border: 1px solid orange;
  color: orange;
  border-radius: 2px;
  margin-right: 20px;
}
.btn-sign:hover {
  cursor: pointer;
}
.btn-sign div {
  width: 30px;
  height: 30px;
  background-image: url('../assets/icon/user.png');
  background-size: contain;
  background-repeat: no-repeat;
  margin-right : 10px;
}
.btn-sign label {
  position: relative;
  top: 4px;
}
.btn-sign label:hover {
  cursor: pointer;
}
.btn-sign:focus {
  outline: none;
}
.btn-cart {
  display: flex;
  align-items: center;
  background: transparent;
  border: 1px solid orange;
  color: orange;
  border-radius: 2px;
  padding: 5px;
}
.btn-cart div {
  width: 30px;
  height: 30px;
  background-image: url('../assets/icon/shopping-cart.png');
  background-size: contain;
  background-repeat: no-repeat;
  margin-right : 10px;
}
.btn-cart label {
  position: relative;
  top: 4px;
}
.btn-cart label:hover {
  cursor: pointer;
}
.btn-cart:hover {
  cursor: pointer;
}
.btn-cart:focus {
  outline: none;
}
.cart-number {
  margin-left: 10px;
  display: flex;
  width: 20px;
  height: 20px;
  align-items: center;
  justify-content: center;
  background-color: orange;
  border: 1px solid orange;
  border-radius: 2px;
  color: #ffffff;
}
</style>
