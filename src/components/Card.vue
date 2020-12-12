<template>
  <div class="card" :style="bgImage()"></div>
</template>

<script>
export default {
  name: "Card",
  props: {
    path: String,
    value: Number,
  },
  methods: {
    bgImage() {
      return `background-image: url(${this.path})`;
    },
  },
};
</script>

<style scoped>
.card {
  width: 100px;
  height: 140px;
  background-repeat: no-repeat;
  background-size: 100%;
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