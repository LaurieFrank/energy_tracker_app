<template lang="html">
  <div>
    <h1>Energy Tracker</h1>
    <energy-tracker :organisedData="organisedData"></energy-tracker>
  </div>
</template>

<script>
import EnergyTracker from './components/EnergyTracker.vue'

export default {
  name: 'app',
  data(){
    return {
      data: {},
      data24: [],
      organisedData: [],
      organisedLineData: []
    }
  },
  components: {
    "energy-tracker": EnergyTracker
  },


  mounted(){
    fetch('https://api.carbonintensity.org.uk/generation')
      .then(response => response.json())
      .then((fetchedData) => {
        this.data = fetchedData.data.generationmix
        let mappedObj = this.data.map((obj) => Object.values(obj))
        mappedObj.unshift(["fuel", "%"]);
        this.organisedData = mappedObj
        }
      )
    fetch('https://api.carbonintensity.org.uk/generation/2018-05-15T12:00Z/pt24h')
      .then(response => response.json())
      .then(data => this.data24 = data.data)

  // .then((fetchedData) => {
    // this.data24 = fetchedData.data.generationmix
    // Object.values(obj)
    // let mappedObj = this.data24.map((obj) => Object.values(obj))
    // mappedObj.unshift(["fuel", "%"]);
    // this.organisedLineData = mappedObj
    // console.log("mapped24Obj", mappedObj);
  // }
// )

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
