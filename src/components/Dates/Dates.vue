<template>
  <div>
    <div class="grid-container-top">
      <div class="grid-item-top"><strong>Mon</strong></div>
      <div class="grid-item-top"><strong>Tue</strong></div>
      <div class="grid-item-top"><strong>Wed</strong></div>
      <div class="grid-item-top"><strong>Thu</strong></div>
      <div class="grid-item-top"><strong>Fri</strong></div>
      <div class="grid-item-top"><strong>Sat</strong></div>
      <div class="grid-item-top"><strong>Sun</strong></div>
    </div>
    <div class="grid-container">
      <div v-bind:key="index" v-for="(date, index) in dates">
        <div class="grid-item">
          <strong>{{ date }}</strong>
        </div>
      </div>
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
  padding: 10%;
  padding-top: 0;
  padding-bottom: 0;
  background: url("../../assets/b3.jpg");
  background-size: 100%;
  background-attachment: fixed;
}

.grid-item {
  /* box-sizing: border-box; */

  border: 1px solid rgba(252, 249, 249, 0.603);
  padding: 20%;
  font-size: calc(0.6vw + 0.8rem);
  color: white;
  text-align: center;
  height: 8vw;
  line-height: 8vw;
  background: url("../../assets/b3.jpg");
  background-size: 100%;
  background-attachment: fixed;
  transition: all 0.25s linear;
}
.grid-item:hover {
  cursor: pointer;

  color: rgb(236, 247, 142);
  border-color: white;
}
.grid-container-top {
  display: grid;
  grid-template-columns: repeat(7, 1fr);
  padding: 10%;
  padding-top: 0;
  padding-bottom: 0;
  background: url("../../assets/b3.jpg");
  background-size: 100%;
  background-attachment: fixed;
}
.grid-item-top {
  border: 1px solid rgba(252, 249, 249, 0.603);
  padding-top: 20%;
  padding-bottom: 20%;
  font-size: calc(0.6vw + 0.8rem);
  color: white;
  text-align: center;
  height: 8vw;
  line-height: 8vw;
  background: url("../../assets/b3.jpg");
  background-size: 100%;
  background-attachment: fixed;
}
@media screen and (min-width: 700px) {
  .grid-item {
    font-size: calc(1vw + 0.8rem);
    border: 3px solid rgba(252, 249, 249, 0.603);
    height: 0.8vw;
    line-height: 0.8vw;
  }
  .grid-container-top {
  }
  .grid-item-top {
    border: 3px solid rgba(252, 249, 249, 0.603);
    height: 0.8vw;
    line-height: 0.8vw;
    font-size: calc(1vw + 0.8rem);
  }
}
@media screen and (max-width: 700px) {
  .grid-container {
    height: 200px;
  }
}
</style>
