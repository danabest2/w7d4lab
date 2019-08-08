<template>
  <div>
    <GChart type="PieChart"
       :data="cData"
       :options="chartOptions"
    />
  </div>
</template>

<script>
  export default{
    name: 'GenerationChart',
    props: ['cData'],
    data() {
      return {

        
        chartOptions: {
          chart: {
            title: 'Energy Generation Chart',
            subtitle: 'Enter timeline here'
          }
        }

      }

    }

  }

</script>

<style lang="css" scoped>
</style>
