<template>
  <div>
   <div style="text-align: center;">
     <h1>Thông tin giỏ hàng </h1>
   </div>
    <table class="table" style="width:700px">
      <thead>
        <tr>
          <th>ProductName</th>
          <th>product_image</th>
          <th>quantity</th>
          <th>unit_price</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item,index) in cart" :key="index">
          <th>{{item.productName}}</th>
          <th>
            <img :src="item.productThumbnail" alt=""  width="150px">
          </th>
          <th>{{item.quantity}}</th>
          <th>{{item.unitPrice}}</th>
        </tr>
      </tbody>
    </table>
    
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
          cart:[]
    };
  },
  methods: {
        callApiCartItem(){
              axios.get("http://localhost:8080/api/v1/cartitems").then((response) => {
                this.cart = response.data;
                console.log(this.cart)
      });
        }
  },
  created() {
        this.callApiCartItem()
  },
};
</script>

<style>

</style>