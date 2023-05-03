<template>

  <div class="black-bg" v-if="modal == true" @click="modal = false">
    <div class="white-bg">
      <h4>{{oneRoomData[modalIndex].title}}</h4>
      <p>{{oneRoomData[modalIndex].content}}</p>
      <p>{{oneRoomData[modalIndex].price}} 원</p>
      <button @click="modal = false">닫기</button>
    </div>
  </div>

  <div class="menu">
    <a v-for="(menu, i) in menuList" :key="i">{{ menu }}</a>
  </div>

  <!-- <div>
    <img :src="oneRoomData[0].image" class="room-img">
    <h4 @click="modal = true, modalIndex = 0" :style ="style">{{ products[0] }}</h4>
    <p> {{ price1 }} 만원</p>
    <button @click="increase(0)">허위 매물 신고</button>
    <span>신고수 : {{ singo[0] }}</span>
  </div>
  <br>
  <div>
    <img :src="oneRoomData[1].image" class="room-img">
    <h4 @click="modal = true, modalIndex = 1" :style = "style2">{{ products[1] }}</h4>
    <p> {{ price2 }} 만원</p>
    <button @click="increase(1)">허위 매물 신고</button>
    <span>신고수 : {{ singo[1] }}</span>
  </div>
  <br>
  <div>
    <img :src="oneRoomData[2].image" class="room-img">
    <h4 @click="modal = true, modalIndex = 2" :style = "style">{{ products[2] }}</h4>
    <p> {{ price1 }} 만원</p>
    <button @click="increase(2)">허위 매물 신고</button>
    <span>신고수 : {{ singo[2] }}</span>
  </div> -->
  
  <!-- 반복문 연습 -->
  <!-- <div class="list" v-for="(a, i) in products" :key="i">
    <h4>{{ a }}</h4>
    <p>{{ priceList[i] }}</p>
  </div> -->

  <div class="list" v-for="(a, i) in products" :key="i">
    <img :src="oneRoomData[i].image" class="room-img">
    <h4 @click="modal = true, modalIndex = i" :style ="style">{{ products[i] }}</h4>
    <p> {{ price1 }} 만원</p>
    <button @click="increase(i)">허위 매물 신고</button>
    <span>신고수 : {{ singo[i] }}</span>
  </div>
</template>

<script>

import oneRoomData from './assets/oneRoom.js'

export default {
  name: 'App',
  data() {
    return {
      price1 : 60,
      price2 : 80,
      priceList : [60, 80, 60],
      logo : '원룸샵',
      style : 'color : blue',
      style2 : 'color : skyblue',
      products : ['신림원룸', '창동원룸', '금산원룸', '무암동원룸', '탄천동원룸', '반지하'],
      menuList : ['Home', 'Shop', 'About'],
      singo : [0,0,0],
      modal : false,
      modalIndex : 0,
      oneRoomData : oneRoomData,
    }
  },
  methods: {
    increase(index) {
      this.singo[index] += 1;
    }
  },
  components: {

  }
}
</script>

<style>
body {
  margin : 0;
}
div {
  box-sizing: border-box;
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

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu {
  background: darkslateblue;
  padding : 15px;
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
