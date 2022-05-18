<template>
  <div class="head">
    <div class="container">
      <div class="row">
        <div class="col-md-3">
          <div class="logo">
            <img src="../asset/logo.svg" alt=""  width="auto"/>
          </div>
        </div>
        <div class="col-md-8">
          <div class="cate">
            <div class="cate-mini">
              <nuxt-link to="/">Trang chủ</nuxt-link>
            </div>
            <div class="cate-mini">
              <nuxt-link to="/Product">Product</nuxt-link>
            </div>
            <div class="cate-mini">
              <nuxt-link to="/Category">Category</nuxt-link>
            </div>
            <div class="cate-mini">Cửa hàng</div>
            <div class="cate-mini">Chia sẻ & kiến thức</div>
            <div class="cate-mini">Liên hệ</div>
          </div>
        </div>
        <div class="col-md-1">
          <div class="cart">
            <nuxt-link to="/cart">
              <img src="../asset/cart.svg" alt="" />
            </nuxt-link>
          </div>
        </div>
        <div>
          
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
.head {
  display: flex;
  justify-content: space-between;
  padding: 40px 20px;
  background-color: #cbaf8f;
}
.cate .cate-mini {
  color: white;
  font-size: 20px;
}
.cate-mini{
  color: white;

}
.cate {
  display: flex;
  justify-content: space-between;
  margin-right: 150px;
}
.cate-mini {
  padding-top: 20px;
  padding-right: 13px;
  padding-left: 10px;
}
.cart {
  margin-top: 14px;
  margin-right: 34px;
  padding-left: 8px;
  padding-right: 34px;
  padding-top: 17px;
  width: 43px;
  height: 50px;
  flex-shrink: 0;
  border-radius: 50%;
  background-color: #bc9f7d;
  position: relative;
}
</style>