<template>
  <div id="app">
    <div class="background">
      <div class="container">
        <div class="dropdown">
          <MonthSelect v-on:onSelect="onSelectMonth" />
          <YearSelect v-on:onSelect="onSelectYear" />
        </div>
        <Dates v-bind:dates="dates" />
      </div>
    </div>
  </div>
</template>

<script>
import moment from "moment";
import Dates from "./components/Dates/Dates";
import MonthSelect from "./components/Dropdown/MonthSelect";
import YearSelect from "./components/Dropdown/YearSelect";
export default {
  name: "App",
  components: {
    Dates,
    MonthSelect,
    YearSelect,
  },
  data() {
    return {
      dates: Array.apply(null, Array(42)),
      month: moment().month(),
      year: moment().year(),
    };
  },
  methods: {
    createCalendar() {
      let startDay = moment(`${this.year}-${this.month + 1}`, "YYYY-MM")
        .startOf("month")
        .day();
      let daysInMonth = moment(
        `${this.year}-${this.month + 1}`,
        "YYYY-MM"
      ).daysInMonth();
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
    onSelectMonth(month) {
      this.month = parseInt(month);
      console.log("out", typeof parseInt(month));
      this.createCalendar();
    },
    onSelectYear(year) {
      this.year = parseInt(year);
      console.log("out", typeof parseInt(year));
      this.createCalendar();
    },
  },
  created() {
    this.createCalendar();
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
}
.container {
  background: url("./assets/b3.jpg");
  background-size: 100%;
  background-attachment: fixed;
}
.background,
html {
  min-height: 100vh;
  background-color: #f0bd12;
}
.dropdown {
  display: flex;
  justify-content: center;
}
@media screen and (max-width: 700px) {
  .container {
    margin-top: 170px;
  }
}
</style>
