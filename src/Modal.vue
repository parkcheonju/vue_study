<template>
  <div class="black-bg" v-if="modal == true">
    <div class="white-bg">
      <img :src="oneroom[click].image" style="width: 50%" />
      <h4>{{ oneroom[click].title }}</h4>
      <p>{{ oneroom[click].content }}</p>
      <p>{{ oneroom[click].price }}</p>
      <button @click="$emit('closeModa')">모달창 닫기</button>
    </div>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line
  name: "Modal",
  props: {
    oneroom : Array,
    click : Number,
    modal : Boolean,
  },
};
</script>

<style>
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
</style>
