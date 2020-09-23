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
    </select>
  </div>
</template>

<script>
export default {
  name: "YearSelect",
  data() {
    return {
      selectedYear: "2020",
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

<style scoped></style>
