<template>
  <Discount v-bind="obj" />
  <Modal @closeModal="modal = false" :oneroom="oneroom" :click="click" :modal="modal" />
  <div class="menu">
    <a v-for="(menu, i) in menus" :key="menu">{{ menus[i] }}</a>
  </div>
  <Card :oneroom="oneroom[i]" v-for="(onerooms, i) in oneroom" :key="onerooms" />
</template>

<script>
import data from "./assets/oneroom";
import Card from "./Card.vue";
import Discount from "./Discount.vue";
import Modal from "./Modal.vue";

export default {
  name: "App",
  data() {
    return {
      obj: { name: "kim", age: 20 },
      menus: ["Home", "Shop", "About"],
      modal: false,
      oneroom: data,
      click: 0,
    };
  },
  methods: {
    increase() {
      this.click_num++;
    },
  },
  components: { Discount, Modal, Card },
};
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
