<template>
  <div>
    <img :src="oneroom.image" class="room-img" />
    <h4>{{ oneroom.title }}</h4>
    <p>{{ oneroom.price }}</p>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line
  name: "Card",
  props: {
    oneroom: Object,
  },
};
</script>

<style></style>
