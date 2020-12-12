<template>
  <div class="card" :style="bgImage()"></div>
</template>

<script>
export default {
  name: "Card",
  props: {
    spritePath: String,
    value: Number,
  },
  methods: {
    bgImage() {
      return `background-image: url(${this.spritePath})`;
    },
  },
};
</script>

<style scoped>
.card {
  width: 200px;
  height: 285px;
  background-size: cover;
  border-radius: 7px;
  box-shadow: 1px 1px 5px rgba(0, 0, 0, 0.5);
  transition: 0.5s;
  cursor: pointer;
}

.card:hover {
  transform: scale(1.1);
  box-shadow: 5px 5px 7px rgba(0, 0, 0, 0.3);
}
</style>