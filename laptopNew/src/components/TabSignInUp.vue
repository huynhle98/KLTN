<template>
  <div id="tab-sign">
      <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'tab-sign',
  data() {
    return {

    }
  }
}
</script>

<style>
.tabs-content {
  background: #fff;
  margin: 2% 0 0 20%;
  padding: 0;
  height: 90%;
  width: 60%;
  border-radius: 4px;
  border: 1px solid #fff;
  text-align: center;
  position: fixed;
  z-index:99999;
  top:0;
  color: #525252;
}
.tab-header {
  display: flex;
  justify-content: space-between;
}
.tab-sign-inup {
  display: flex;
  margin: 0;
  padding: 0;
  list-style: none;
}
.tab-sign-inup li {
  padding: 10px 20px;
  font-size: 18px;
  font-weight: 300;
  width: 130px;
  color: #dcded0;
}
.tab-sign-inup li:hover {
  cursor: pointer;
}
.tab-sign-inup .active {
  color: orange;
  background-color: #fff;
  border-bottom: 1px solid orange;
}
.tab-sign-inup .active:hover{
  color: orange !important;
  background-color: #fff !important;
}
.sign-in {

}
.sign-in >label {
    font-size: 22px;
    font-weight: bold;
    color: rgb(13, 121, 189);
}
.login-close {
    margin: 2%;
    float: right;
    color: transparent;
    background-color: transparent;
    border: none;
    width: 15px;
    height: 15px;
    text-decoration: none;
    background:
    linear-gradient(to top left,
        rgba(0,0,0,0) 0%,
        rgba(0,0,0,0) calc(50% - 1.2px),
        rgba(0,0,0,1) 50%,
        rgba(0,0,0,0) calc(50% + 1.2px),
        rgba(0,0,0,0) 100%),
    linear-gradient(to top right,
        rgba(0,0,0,0) 0%,
        rgba(0,0,0,0) calc(50% - 1.2px),
        rgba(0,0,0,1) 50%,
        rgba(0,0,0,0) calc(50% + 1.2px),
        rgba(0,0,0,0) 100%);
}
.close-background{
    margin: 1%;
    width: 25px;
    height: 25px;
    background-color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    float: right;
}
.close-background:hover {
    cursor: pointer;
}
.login-close:hover {
  cursor: pointer;
    background:
    linear-gradient(to top left,
        rgba(0,0,0,0) 0%,
        rgba(0,0,0,0) calc(50% - 1.2px),
        rgb(255, 0, 0) 50%,
        rgba(0,0,0,0) calc(50% + 1.2px),
        rgba(0,0,0,0) 100%),
    linear-gradient(to top right,
        rgba(0,0,0,0) 0%,
        rgba(0,0,0,0) calc(50% - 1.2px),
        rgb(255, 0, 0) 50%,
        rgba(0,0,0,0) calc(50% + 1.2px),
        rgba(0,0,0,0) 100%);
}
.login-close:focus {
  outline: none;
}
.login-main {
    display: flex;
    flex-direction: row;
    height: auto;
    width: 100%;
    background: #f1f0f1;

}
.login-left {
    height: auto;
    width: 40%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    text-align: center;
    background-color: #fff;
    padding-top: 3%;
    padding-bottom: 10%;
    border: 1px solid #f1f0f1;
    border-radius: 0 0 0 4px;
}
.login-left div{
    height: 150px;
    width: 150px;
    background-image: url('../assets/signinup/login_icon.png');
    background-size: cover;
    background-position: center;
    margin-top: 13%;
}
.login-content {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    height: auto;
    width: 60%;
    padding-top: 3%;
    padding-bottom: 5%;
    background-color: #fff;
    border: 1px solid #f1f0f1;
    border-radius: 0 0 4px 0;
}
.login-item {
    margin-bottom: 10px;
    padding: 8px;
    padding-top: 10px;
    width: 80%;
    border: 1px solid #ccc;
    border-radius: 4px;
    outline: 0;
    font-size: 13px;
    padding-left: 1.0em;
}
.login-item:focus{
    border: 1px solid rgb(27, 168, 255);
}
.login-content div {
  display: flex;
  width: 80%;
}
.login-content div label {
  padding-top: 10px;
  margin-left: -10px;
  margin-right: 20px;
}
.select-sex {
  margin-bottom: 10px;
  padding: 8px;
  padding-top: 10px;
  width: 130px;
  border: 1px solid #ccc;
  border-radius: 4px;
  outline: 0;
  font-size: 13px;
  padding-left: 1.0em;
}
.login-item-forget {
    border: none;
    text-decoration: none;
    color: rgb(27, 168, 255);
    font-weight: bolder;
    font-size: 11px;
    justify-content: left;
    display: flex;
    margin-bottom: 3%;
}
.login-item-forget:hover {
    color: rgb(11, 126, 197);
}
.login-item-forget:focus {
    border: none;
}
button.login-item  {
    border: 1px solid rgb(253, 216, 53);
    background-color: white;
    color: rgb(253, 216, 53);
    width: 60%;

}
button.login-item:hover {
    background-color: rgb(253, 216, 53);
    color: #333;
    cursor: pointer;
}
button.login-item:focus {
    border: 1px solid rgb(253, 216, 53);
}
.login-content >label {
    font-size: 11px;
    font-weight: bolder;
    color: #333;
    margin-top: 3%;
    margin-bottom: 2%;
}
.login-item-fb {
    margin-bottom: 10px;
    padding: 7px;
    border: 1px solid rgb(59, 89, 152);
    background-color: white;
    color: rgb(59, 89, 152);
    border-radius: 4px;
    outline: 0;
    font-size: 13px;
    width: 50%;
}
.login-item-fb:hover {
    background-color: rgb(59, 89, 152);
    color: #fff;
    cursor: pointer;
}
.login-item-gg {
    margin-bottom: 10px;
    padding: 7px;
    border: 1px solid rgb(223, 74, 50);
    background-color: white;
    color: rgb(223, 74, 50);
    border-radius: 4px;
    outline: 0;
    font-size: 13px;
    width: 50%;
}
.login-item-gg:hover {
    background-color: rgb(223, 74, 50);
    color: #fff;
    cursor: pointer;
}
#over {

    background: #333;
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    opacity: 0.8;
    z-index: 999;
}
</style>
