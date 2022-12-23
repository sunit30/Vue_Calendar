<template>
  <div>
    <select name="year" @change="onSelect()" v-model="selectedYear">
      <!-- <option disabled value="">Select year</option> -->
      <option value="2010">2010</option>
      <option value="2011">2011</option>
      <option value="2012">2012</option>
      <option value="2013">2013</option>
      <option value="2014">2014</option>
      <option value="2015">2015</option>
      <option value="2016">2016</option>
      <option value="2017">2017</option>
      <option value="2018">2018</option>
      <option value="2019">2019</option>
      <option value="2020">2020</option>
      <option value="2021">2021</option>
      <option value="2022">2022</option>
      <option value="2023">2023</option>
    </select>
  </div>
</template>

<script>
import moment from "moment";
export default {
  name: "YearSelect",
  data() {
    return {
      selectedYear: `${moment().month()}`,
    };
  },
  methods: {
    onSelect: function() {
      this.$emit("onSelect", this.selectedYear);
      console.log(this.selectedYear);
    },
  },
};
</script>

<style scoped>
select {
  background-color: #f0bd12;
  color: white;
  padding: 3px;
  font-weight: 600;
  font-size: 1.2rem;
  margin: 5px;
}
option {
  font-weight: 600;
  font-size: 1.2rem;
}
</style>
