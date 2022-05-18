<template>
  <div>
    <ul>
    
      
    </ul>
        <table class="table">
      <thead>
        <tr>
          <th>ID</th>
          <th>Tên thể loại</th>
          <th>Chi tiết</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(item, index) in dataCate" :key="index">
          <th>{{ item.id }}</th>
          <th>{{ item.name }}</th>
          <th>Thông tin chi tiết từng sản phẩm</th>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import axios from "axios";

export default {
      data(){
            return{
      dataCate: [],

            }
      },
      methods:{
              callApiCategory() {
      axios.get("http://localhost:8080/api/v1/categories").then((response) => {
        this.dataCate = response.data;
      });
    },
      },
      created(){
    this.callApiCategory();

      }
}
</script>

<style>

</style>