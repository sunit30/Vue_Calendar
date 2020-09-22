<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App" />
    {{ dates }}
    <Dates v-bind:dates="dates" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import moment from "moment";
import Dates from "./components/Dates/Dates";
export default {
  name: "App",
  components: {
    HelloWorld,
    Dates,
  },
  data() {
    return {
      dates: Array.apply(null, Array(42)),
    };
  },
  created() {
    let startDay = moment()
      .startOf("month")
      .day();
    let daysInMonth = moment().daysInMonth();
    //"2016-02", "YYYY-MM"
    if (startDay == 0) {
      startDay = 7; //for monday as week starter
    }
    let count = 0;
    this.dates = this.dates.map((day, i) => {
      if (i >= startDay - 1 && i <= startDay - 1 + daysInMonth - 1) {
        count = count + 1;
        return count;
      } else {
        return;
      }
    });
    //console.log(this.dates);
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
