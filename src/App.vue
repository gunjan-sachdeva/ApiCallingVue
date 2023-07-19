<template>
  <h1>Call Api</h1>
  <!-- <p v-for='item in list' :key="item">
  {{item.id}} --- {{item.email}} ---

  {{item.first_name}}
  </p> -->

  <ul class="item" v-for="item in list" :key="item.id">
  <li>
  {{item.id}}
  </li>
  <li>
  {{item.email}}
  </li>
  <li>
  {{item.first_name}}
  </li>
  <li>
<img :src="item.avatar" />
  </li>
  
  </ul>
</template>

<script>

import axios from 'axios';
export default {
  name: 'App',
 data()
 {
  return{
    list:[]
  }
 },
 async mounted()
 {
  let result=await axios.get("https://reqres.in/api/users?page=1")
  console.warn("api data",result.data.data);
  this.list=result.data.data
 }
}
</script>

<style scoped>
.item{
  display: flex;
}
.item img{
  width: 50px;
}
.item li{
  display: inline-block;
  width: 180px;
  border: 1px solid red;
  text-align: center;
  padding: 5px;
}
</style>


