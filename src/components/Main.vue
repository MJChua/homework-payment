<template>
  <div class="main">
    <div class="shop">
      <div class="shop-wrapper">
        <div class="shop-head">
          <div class="shop-head-title bold">
            <span>購物車</span>
          </div>
          <div class="shop-head-baseline"></div>
        </div>
        <div class="shop-main">
          <div class="shop-main-nav flex-row">
            <div class="shop-main-nav-name fz-18 black bold">商品名稱</div>
            <div class="shop-main-nav-quant fz-18 black bold">數量</div>
            <div class="shop-main-nav-price fz-18 black bold">售價</div>
            <div class="shop-main-nav-discount fz-18 black bold">折扣</div>
            <div class="shop-main-nav-real-pay fz-18 black bold">實付價格</div>
            <div class="shop-main-nav-remove fz-18 black bold">移除</div>
          </div>
          <div class="shop-main-product flex-row">
            <div class="shop-main-product-name">
              經典口金後背包《法國色》 L尺寸
            </div>
            <div class="shop-main-product-quant">
              <select name="quant" id="quant">
                <option value="1">1</option>
                <option value="2">2</option>
                <option value="3">3</option>
                <option value="4">4</option>
                <option value="5">5</option>
              </select>
            </div>
            <div class="shop-main-product-price">16,400</div>
            <div class="shop-main-product-discount">400</div>
            <div class="shop-main-product-real-pay">16,000</div>
            <div class="shop-main-product-remove">
              <a href="javascript:;">
                <img src="@/assets/icons/deleter.svg" alt="trashCan" />
              </a>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Main"
};
</script>

<style lang="stylus">
.main
  width 1440px
  // Common Css
  .flex-row
    display flex
    flex-direction row
  .flex-col
    display flex
    flex-direction column
  .fz-18
    font-size 18px
  .bold
    font-weight bold
  .black
    color #333333
  // Common Css End
  .shop
    &-wrapper
      width 100%
      .shop-head
        &-title
          text-align left
          margin-bottom 18px
          span
            font-size 24px
            font-family Segoe UI
            padding 0 3px
        &-baseline
          width 100%
          height 3px
          background #30303a
          margin-bottom 21px
    .shop-main
      width 100%
      &-nav
        padding 13px 50px
        background #E8E8E8
        margin-bottom 6px
        justify-content space-between
        &-name
          margin-right 239px
        &-quant
          margin-right 120px
      &-product
        padding 13px 50px
        margin-bottom 6px
        justify-content space-between
        align-items center
        text-align left
        &-name
          word-break keep-all
          width 300px
          // margin-right 60px
        &-quant
          width 105px
          margin-right 20px
        &-price
          width 100px
          text-align center
          // margin-right 109px
        &-discount
          width 50px
          text-align center
          // margin-right 124px
        &-real-pay
          width 100px
          text-align center
          // margin-right 140px
        &-remove
          width 24px
</style>
