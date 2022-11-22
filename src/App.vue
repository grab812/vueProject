<template>

  <modalView v-if="modalState" @close-modal="modalState = false">

  </modalView>


  <div class="menu">
    <a v-for="menuTab in manuTabs" :key="menuTab">{{menuTab}}</a>
  </div>


  <!-- <div v-for="(item,i) in rooms" :key="i">
    <img :src="require(`@/assets/room${i}.jpg`)" alt="" class="room-img">
    <h4 @click="modalState = !modalState">{{item.product}}</h4>
    <p>가격 : {{item.price}}만원</p>
    <button @click="checkNum[i]++">허위매물신고</button><span>신고수: {{checkNum[i]}}</span>
  </div> -->

  <div v-for="(item,i) in onerooms" :key="i" @click="info($event, i)">
    <img :src="onerooms[i].image" alt="" class="room-img">
    <h4 v-html="this.onerooms[i].price"></h4>
    <p>가격 : {{onerooms[i].price}}만원</p>
    <!-- <button @click="checkNum[i]++">허위매물신고</button><span>신고수: {{checkNum[i]}}</span> -->
  </div>
</template>

<script>
// import 작명 from "경로";
// import { 변수 } from "./data/post.js";

// import oneroomDate from "./data/oneroomDate.js"; 확장자 생략가능
import oneroomDate from "./data/oneroomDate";
import modalView from "./components/modalView";

export default {
  name: 'App',
  components: {
    modalView,
  },
  // 데이터바인딩
  data() {
    return {
      selected: '',
      modalState: false,
      manuTabs: ["Home", "Product", "About"],
      rooms: [
        {product: '마포구원룸', price:50},
        {product: '노원구원룸', price:90},
        {product: '장안구원룸', price:70},
      ],
      checkNum: [0,2,0],
      onerooms: oneroomDate,
    }
  },
  // 함수 function
  methods: {
    increase(){
      this.checkNum++;
    },
    info(item,i){
      // tit.innerText = this.onerooms[i].title;
      this.modalState = !this.modalState;
      console.log(this.modalState,this.onerooms[i].price, i);
    }
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
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
.menu {
  background: salmon;
  border-radius: 10px;
  padding: 10px;
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
