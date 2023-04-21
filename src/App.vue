<template>
  <div class="black-bg" v-if="modal == 1">
    <div class="white-bg">
      <h4>{{oneroom[click].title}}</h4>
      <p>상세페이지내용</p>
      <button @click="modal = false">모달창 닫기</button>
    </div>
  </div>
  <div class="menu">
    <a v-for="menu in menus" :key="menu">{{ menu }}</a>
  </div>
  <div v-for="(a, i) in oneroom" :key="i">
    <img :src="a.image" class="room-img">
    <h4 @click="modal = true; click = i">{{a.title}}</h4>
    <p>{{a.price}}</p>
  </div>

</template>

<script>
import data from "./assets/oneroom";
export default {
  name: "App",
  data() {
    return {
      modal: false,
      oneroom: data,
      click:0,
    };
  },
  methods: {
    increase() {
      this.click_num++;
    },
  },
  components: {},
};
</script>

<style>
body {
  margin: 0;
}
div {
  box-sizing: border-box;
}
.black-bg {
  width: 100%;
  height: 100%;
  background: rgba(0, 0, 0, 0.5);
  position: fixed;
  padding: 20px;
}
.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding: 20px;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.menu {
  background-color: darkslateblue;
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
