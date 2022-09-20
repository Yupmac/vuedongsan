<template>
  <!-- 모달창 -->
  <Modal :products="products" :choice="choice" :modal="modal" />

  <!-- 네비바 -->
  <div class="menu">
    <a v-for="(a,i) in menu" :key="i">{{ a }}</a>
  </div>

  <!-- 할인배너 -->
  <Discount />

  <!-- 상품메뉴 -->
  <Card :products="products" />
  <!-- <div v-for="(data,i) in products" :key="i">
    <img :src="data.image" class="room-img">
    <h4 @click="modal = true; choice = i">{{ data.title }}</h4>
    <p>{{ data.price }}만원</p>
  </div> -->

</template>

<script>
import data from './database.js'
import Discount from './components/Discount.vue'
import Modal from './components/Modal.vue'
import Card from './components/Card.vue'


export default {
  name: 'App',
  data() {
    return {
      modal : false,
      choice : 0,
      menu : ['Home', 'Shop', 'About'],
      products : data,
    }
  },
  methods : {
    increase() {
      this.count += 1;
    }
  },

  components: {
    Discount : Discount,
    Modal : Modal,
    Card : Card,
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

body {
  margin : 0;
}
div {
  box-sizing: border-box;
}

.discount {
  background: #eee;
  padding: 10px;
  margin: 10px;
  border-radius: 5px;
}

.black-bg {
  width: 100%; height:100%;
  background: rgba(0,0,0,0.5);
  position: fixed; padding: 20px;
}
.white-bg {
  width: 100%; background: white;
  border-radius: 8px;
  padding: 20px;
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

.room-img {
  width: 100%;
  margin-top: 40px;
}

</style>
