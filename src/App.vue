<template lang="html">
  <div>
    <h1>Energy Tracker</h1>
    <energy-tracker :energyTypes="energyTypes"></energy-tracker>
    <GChart
    type="ColumnChart"
    :data="chartData"
    :options="chartOptions"
    />
  </div>
</template>

<script>
import EnergyTracker from './components/EnergyTracker.vue'
import { GChart } from 'vue-google-charts'

export default {
  name: 'app',
  data(){
    return {
      energyData: {},
      sortedEnergyData: []
    }
  },
  components: {
    "energy-tracker": EnergyTracker
      },
  mounted(){
    fetch('https://api.carbonintensity.org.uk/generation')
    .then(response => response.json())
    // .then(energyData => this.data.generationmix = energyData)
    .then(console.log(response))


    // .then(this.sortedEnergyData.push(this.energyData.map(object) = Object.values(object)))
    }
  }
  </script>

  <style lang="css" scoped>
  </style>





  // return {
  //   "data":[
  //     {
  //       "from": "2018-01-20T12:00Z",
  //       "to": "2018-01-20T12:30Z",
  //       energyTypes: [
  //         {"fuel": "Milk", "perc": 0.1},
  //         {"fuel": 'Cheese', "perc": 2.2},
  //         {"fuel": 'Beans', "perc": 17.9}
  //       ],
  //       chartOptions: {
  //         chart: {
  //           title: "Energy Types and Usages",
  //           subtitle: "Milk, Cheese, Beans"
  //         }
  //       }
  //     }]
  //   };
