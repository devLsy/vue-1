<template>

  <!-- modal -->
  <div class="black-bg" v-if="showModal">
    <div class="white-bg">
      <h4>상세화면</h4>
      <p>상세 내용</p>
    </div>
    <button @click="showModal = false">close</button>
  </div>

  <div class="menu">
    <a v-for="item in menus" :key="item">{{ item}}</a>
  </div>

  <!-- <div v-for="(item, i) in products" :key="item"> -->
  <div>
    <img src="https://thumb.mt.co.kr/06/2022/04/2022041908320494725_1.jpg/dims/optimize" class="img">
    <h4 @click="showModal = true">{{ products[0]}}</h4>
  </div>    
  <div> 
    <img src="https://d2qgx4jylglh9c.cloudfront.net/kr/wp-content/uploads/2019/09/ironman-e1569489910569.jpg">
    <h4>{{ products[1]}}</h4>
  </div>    
  <div>
    <img src="https://image.kmib.co.kr/online_image/2016/1101/201611012221_13200923635585_1.jpg">
    <h4>{{ products[2]}}</h4>
  </div>    
</template>

<script>


export default {
  name: 'App',
  data() {
    return {
      showModal: false,
      counter: [0,0,0],
      products: ['thor', 'ironMan', 'doctor strange'],
      menus: ['Home', 'Shop', 'About'],
    }
  },
  methods: {
    add() {
      this.counter ++;
    },  
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
