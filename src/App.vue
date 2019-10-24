<template lang="html">
  <div>
    <h1>Energy Tracker</h1>
    <energy-tracker :energyTypes="energyTypes"></energy-tracker>
  </div>
</template>

<script>
import EnergyTracker from './components/EnergyTracker.vue'

export default {
  name: 'app',
  data(){
    return {
      "data":[
        {
      "from": "2018-01-20T12:00Z",
      "to": "2018-01-20T12:30Z",
      energyTypes: [
        {"fuel": "Milk", "perc": 0.1},
        {"fuel": 'Cheese', "perc": 2.2},
        {"fuel": 'Beans', "perc": 17.9}
      ],
    }]
  };
  components: {
    "energy-tracker": EnergyTracker
  }

}
</script>

<style lang="css" scoped>
</style>
