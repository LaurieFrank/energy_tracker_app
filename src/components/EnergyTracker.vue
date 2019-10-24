<template lang="html">
  <div id="energyTracker">
    <GChart
    type="ColumnChart"
    :data="organisedData"
    :options="chartOptions"
    />
  </div>
</template>

<script>
import { GChart } from 'vue-google-charts'


export default {
  name: "energy-tracker",

props: ["organisedData"]
}
</script>

<style lang="css" scoped>
</style>
