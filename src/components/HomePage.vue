<script>
import axios from 'axios'

export default{
  data(){
    return{
      items:[]
    }
  },
  methods:{
    getData(){
      axios.get('https://api.nuxtjs.dev/rivers').then((response) => {
        this.items = response.data
      })
    }
  },
  created(){
    this.getData()
  }

}
</script>

<template>
  <section>
    <div v-for="item in items" :key="item" class="wrapper">
      <ul class="img">
        <li><img :src="item.image" :alt="item.title"></li>
      </ul>
      <ul class="charcters">
        <li class="title">{{ item.title }}</li>
        <br>
        <li class="description">{{ item.description }}</li>
        <br>
        <li class="country">{{ item.countries[0] }}</li>
        <br>
        <li class="length">{{ item.length }}</li>
      </ul>
    </div>
  </section>
</template>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  list-style: none;
  text-decoration: none;
}
.wrapper{
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  height: 100vh;
}
.img{
  width: 50%;
}
.title{
  font-size: 61px;
  margin-left: 120px;
}
.description{
  margin-left: 120px;
  font-size: 20px;
}
.country{
  margin-left: 120px;
  font-size: 20px;
}
.length{
  margin-left: 120px;
  font-size: 20px;
}
</style>
