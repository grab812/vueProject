<template>
  <div class="black-bg">
      <div class="white-bg" >
          <!-- <h4 >{{onerooms[i].title}}</h4>
          <p>{{onerooms[i].price}}</p> -->
          <button class="modalClose" @click="$emit('close-modal')">닫기</button>
      </div>
  </div>
</template>
<script>
export default {
  name: 'modalView',
  // 데이터바인딩
  data() {
    return {
      modalState: false,
    }
  },
};
</script>
<style>
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, .5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  position: relative;
  width: 100%;
  background: rgba(255, 255, 255, 1);
  border-radius: 8px;
  padding: 20px;
}
.modalClose {
  position: absolute;
  top: 3px;
  right: 3px;
  width: 18px;
  height: 18px;
  text-indent: -9999px;
  font-size: 0;
  line-height: 0;
  padding: 5px;
  box-sizing: content-box;
  border: none;
  background-color: transparent;
}
.modalClose:before, .modalClose:after {
  position: absolute;
  top: 0;
  left: 13px;
  content: ' ';
  height: 30px;
  width: 2px;
  background-color: #000000;
}
.modalClose:before {
  transform: rotate(45deg);
}
.modalClose:after {
  transform: rotate(-45deg);
}
</style>