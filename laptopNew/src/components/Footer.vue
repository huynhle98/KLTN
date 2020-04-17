<template>
  <footer id="comp-footer">
            <div class="footer-info">
                <div>HỖ TRỢ KHÁCH HÀNG
                    <label class="label-frist">Hottline hỗ trợ: 1900 1530</label>
                    <label>Gmail: hotro@gmail.com</label>
                    <label>Hướng dẫn đặt hàng</label>
                    <label>Chính sách</label>
                </div>
                <div>THÔNG TIN
                    <label class="label-frist">Giới thiệu</label>
                    <label>Tuyển dụng</label>
                    <label>Điều khoản sử dụng</label>
                </div>
                <div>PHƯƠNG THỨC THANH TOÁN
                    <label>Tiền mặt</label>
                </div>
                <div>KẾT NỐI
                    <a class="footer-fb" href="http://facebook.com">f</a>
                    <a class="footer-zalo" href="https://chat.zalo.me/">Zalo</a>
                </div>
            </div>
            <div class="footer-adress">
                <label class="footer-adress-frist">Địa chỉ: </label>
                <label>88 Trương Văn Thành, phường Hiệp Phú, Quận 9, Tp.HCM</label>
            </div>
            <div class="footer-copyright">©2020</div>
        </footer>
</template>

<script>
export default {
  name: 'comp-footer',
  data () {
    return {

    }
  },
}
</script>

<style>
footer {
    display: inline-block;
    width: 100%;
    height: auto;
    background-color: white;
    text-align: center;
    position: relative;
    top: 150px;
    border-top: 2px solid orange;
}
.footer-info{
    width: 100%;
    display: inline-block;
}
.footer-info >div{
    float: left;
    padding: 5% 6% 5% 6%;
    display: flex;
    flex-direction: column;
    text-align: left;
    color: #333;
    font-weight: bold;

}
.footer-info >div >label{
    color: rgb(63, 63, 63);
    font-size: 13px;
    margin-top: 6px;
    font-weight: normal;

}
.footer-fb {
    margin-top: 10px;
    background-color: rgb(59, 89, 152);
    color: white;
    text-decoration: none;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 35px;
    height: 35px;
    border-radius: 5px;
    font-size: 20px;
    font-weight: bold;
}
.footer-fb:hover {
  text-decoration: none;
  color: white;
}
.footer-zalo {
    margin-top: 5px;
    background-color: #fff;
    color: #5fa0ff;
    border: 1px solid #5fa0ff;
    text-decoration: none;
    display: flex;
    align-items: center;
    justify-content: center;
    width: 35px;
    height: 35px;
    border-radius: 5px;
    padding: 3px;
    font-size: 13px;
    font-weight: bold;
}
.footer-zalo:hover {
  text-decoration: none;
  color: #5fa0ff;
}
.footer-adress{
    font-weight: bolder;
}
.footer-adress-frist {
    color: #333;
    font-weight: bold;
}
.footer-copyright {
    padding-top: 10px;
    padding-bottom: 30px;
    font-weight: bolder;
}
</style>
