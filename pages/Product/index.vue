<template>
  <div style="width: 1140px">
    <div class="container">
      <div class="row">
        <div class="title">
          <h3>Nến thơm</h3>
          <p class="below"></p>
        </div>
        <div class="col-md-3" v-for="(item, index) in dataProduct" :key="index">
          <div class="product">
            <img
              src="https://firstsight.vn/wp-content/uploads/2021/07/candle-cup-nen-thom-nao-tot-de-bao-quan.jpg"
              alt=""
              width="100%"
              height="280px"
            />
            <div class="info">
              <div>
                {{ item.name }}
              </div>
              <div>
                {{item.price}}
              </div>
              <div>
                <button @click="addToCart(item)">Thêm vào giỏ hàng</button>
              </div>
            </div>
          </div>
        </div>
      </div>
      <table class="table">
        <thead>
          <tr>
            <th>ID</th>
            <th>name</th>
            <th>thumbnail</th>
            <th>description</th>
            <th>price</th>
            <th>slug</th>
            <!-- <th>status</th> -->
          </tr>
        </thead>
        <tbody>
          <tr v-for="(item, index) in dataProduct" :key="index">
            <th>{{ item.id }}</th>
            <th>{{ item.name }}</th>
            <th>
              <img :src="item.thumbnail" alt="" width="200px" />
            </th>
            <th>{{ item.description }}</th>
            <th>{{ item.price }} $</th>
            <th>{{ item.slug }}</th>
            <!-- <th>{{ item.status }}</th> -->
            <th>
              <button @click="addToCart(item)">Thêm vào giỏ hàng</button>
            </th>
          </tr>
        </tbody>
        <!-- {{allProduct}} -->
      </table>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      dataProduct: [],
      objPerson: {
        userId: "1",
        cartItemDTOSet: [
          {
            productId: "",
            quantity: 1,
            status: 1,
          },
        ],
      },
    };
  },
  methods: {
    callApiProduct() {
      axios.get("http://localhost:8080/api/v1/products").then((response) => {
        this.dataProduct = response.data.content;
        this.allProduct = response.data;
      });
    },
    addToCart(item) {
      this.objPerson.cartItemDTOSet[0].productId = item.id;
      // this.objPerson.cartItemDTOSet[0].status=item.status;
      console.log(this.objPerson);
      axios
        .post("http://localhost:8080/api/v1/shoppingCart", this.objPerson)
        .then((response) => {
          console.log(response);
        });
    },
  },
  created() {
    this.callApiProduct();
  },
};
</script>

<style>
.title {
  margin-top: 30px;
  margin-bottom: 30px;
}
.below {
  width: 60px;
  background-color: burlywood;
  height: 3px;
}
.product {
  background-color: #f4f4f4;
  height: 350px;
  margin-bottom: 20px;
}
.container {
  /* width: 1140px; */
}
</style>