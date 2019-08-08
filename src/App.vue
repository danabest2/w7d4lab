<template>
  <div id="app">
    <p>Generation Analysis</p>
    <generation-list :data='data' :chartData='chartData'></generation-list>
    <generation-chart :cData='chartData'></generation-chart>
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
      data: [],
      chartData: []
    };
  },
  components: {
    GChart,
    "generation-list": GenerationList,
    "generation-chart": GenerationChart
  },
  methods: {
    getChartFormat: function(data){
      let x = data.data.generationmix;
      let y = x.map(item => [item.fuel, item.perc]);
      y.unshift(["Fuel","Percentage"]);
      return y;
    }
  },
mounted(){
  fetch('https://api.carbonintensity.org.uk/generation')
  .then(res => res.json())
  .then(data => this.data = data)
  .then(data2 => {
    this.chartData = this.getChartFormat(this.data);
  });



}

}

</script>

<style>

</style>
