<template>
  <div>
    <select name="month" @change="onSelect()" v-model="selectedMonth">
      <!-- <option disabled value="">Select month</option> -->
      <option value="0">January</option>
      <option value="1">February</option>
      <option value="2">March</option>
      <option value="3">April</option>
      <option value="4">May</option>
      <option value="5">June</option>
      <option value="6">July</option>
      <option value="7">August</option>
      <option value="8">September</option>
      <option value="9">October</option>
      <option value="10">November</option>
      <option value="11">December</option>
    </select>
  </div>
</template>

<script>
export default {
  name: "MonthSelect",
  data() {
    return { selectedMonth: "1" };
  },
  methods: {
    onSelect: function() {
      this.$emit("onSelect", this.selectedMonth);
      console.log(this.selectedMonth);
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
