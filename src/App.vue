<template>
  <div id="app">
    <p>Generation Analysis</p>
    <generation-list :data='data'></generation-list>
    <generation-chart></generation-chart>
  </div>
</template>

<script>
import GenerationList from './components/GenerationList.vue';
import GenerationChart from './components/GenerationChart.vue';
import { GChart } from 'vue-google-charts'

export default {
  name: 'app',
  data(){
    return {
      data: []
    };
  },
  components: {
    GChart,
    "generation-list": GenerationList,
    "generation-chart": GenerationChart
  },

mounted(){
  fetch('https://api.carbonintensity.org.uk/generation')
  .then(res => res.json())
  .then(data => this.data = data)
}
// ,
// methods(){
//
// }
}



</script>

<style>

</style>
