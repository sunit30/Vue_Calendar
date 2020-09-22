<template>
  <div class="grid-container">
    <div v-bind:key="index" v-for="(date, index) in dates">
      <div class="grid-item">{{ date }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Dates",
  components: {},
  data() {
    return {};
  },
  created() {},
  props: ["dates"],
};
</script>

<style scoped>
.grid-container {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  background-color: #2196f3;
  padding: 10%;
}

.grid-item {
  /* box-sizing: border-box; */
  background-color: rgba(255, 255, 255, 0.8);
  border: 1px solid rgba(0, 0, 0, 0.8);
  padding: 20%;
  font-size: calc(1.5vw + 1rem);
  text-align: center;
  height: 8vw;
  line-height: 8vw;
}
</style>
