<template lang="html">
  <div id="energyTracker">
<VueGoogleCharts
  type="LineChart"
  :data="chartData"
  :options="chartOptions"
  />
  </div>
</template>

<script>
import { eventBus } from '../main.js'

export default {
  name: "energy-tracker"
},
props: ["energyTypes"]
// methods: {
//   drawChart
}
</script>

<style lang="css" scoped>
</style>
