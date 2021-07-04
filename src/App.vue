<template>
  <div id="app">
    <ul>
      <li v-for="(item,index) in users" :key="index">
        {{item.name}}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'App',
  data(){
    return {
      users:[]
    }
  },
  mounted() {
    axios.get('http://localhost:3000/api/user').then((res)=>{
      this.users = res.data
    })
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
ul,li{
  list-style: none;
}
</style>
