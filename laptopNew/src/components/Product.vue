<template>
  <div id='comp-product' class="item">
                        <a class="item-img" href="#"></a>
                        <a class="item-title" href="#">Laptop Gaming Acer Nitro 5 2019 AN515-43 R84R</a>
                        <div class="item-price">18,990,000 đ</div>
                        <div class="item-total-price">
                            <div class="item-pricenew">16,900,000 đ</div>
                            <div class="item-discount">-11%</div>
                        </div>
                        <div class="item-comment">
                            <label>(5 nhận xét)</label>
                        <span style="width:95%">
                                    <i class="star"></i>
                                    <i class="star"></i>
                                    <i class="star"></i>
                                    <i class="star"></i>
                                    <i class="star"></i>
                                </span>
                        </div>
                </div>
</template>

<script>
export default {
  name: 'comp-product',
  data () {
    return {
    }
  },
}
</script>

<style>
.item {
    display: inline-block;
    width: 230px;
    height: 400px;
    background: white;
    margin: 15px 0 0 5px;
    font-weight: bolder;
}
.item:hover {
    box-shadow: 1px 1px 10px 4px #e2e2e2;
}
.item-img {
    display: flex;
    position: relative;
    width: 230px;
    height: 200px;
    background-size: contain;
    background-repeat: no-repeat;
    background-position: center;
    transition: all .1s ease-in-out;
    background-image: url('../assets/demo/item_demo.jpg');
}
.item-title {
    display: block;
    color: #333;
    font-size: 18px;
    font-weight: bold;
    padding: 10px;
    text-decoration: none;
}
.item-title:hover{
    text-decoration: none;
    color: rgb(4, 33, 114);
}
.item-price {
    text-decoration: line-through;
    font-size: 12px;
    margin-top: 10px;
    margin-left: 10px;
}
.item-total-price {
    display: flex;
    flex-direction: row;
    align-items: center;
    margin-left: 10px;

}
.item-pricenew {
    color: red;
    font-size: 15px;
    font-weight: bold;
}
.item-discount {
    font-size: 12px;
    color: #333;
    margin-left: 10px;
}
.item-comment {
    margin-top: 10px;
    margin-left: 10px;
    font-size: 12px;
}
</style>
