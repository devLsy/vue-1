<template>
  <!-- modal -->
  <div class="black-bg" v-if="showModal">
    <div class="white-bg">
      <h4>상세화면</h4>
      <p>상세 내용</p>
      <button @click="showModal = false">close</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="item in menus" :key="item">{{ item}}</a>
  </div>

  <h1>어흥 부동산</h1>

  <div v-for="(item, i) in rooms" :key="item">
    <img :src="rooms[i].image" class="img">
    <h4 @click="showModal = true">{{ rooms[i].title }}</h4>
    <p>{{ rooms[i].content }}</p>
    <p>가격: {{ rooms[i].price }}원</p>
  </div>      
</template>

<script>

import data from './assets/oneroom.js';

export default {
  name: 'App',
  // state
  data() {
    return {
      rooms: data,
      showModal: false,
      counter: [0,0,0],
      products: ['thor', 'ironMan', 'doctor strange'],
      menus: ['Home', 'Shop', 'About'],
    }
  },
  methods: {
    
  },
  components: {
    
  } 
}
</script>

<style>

body {
  margin: 0;
}

div {
  box-sizing: border-box;
}

.black-bg {
  width: 100%; height: 100%;
  background: rgba(0,0,0,0,.5);
  position: fixed; padding: 20px;
}

.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;

}

.menu {
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a {
  color: white;
  padding: 10px;
}

.img {
  width: 100%;
  margin-top: 40px;
}



</style>
