<template>
  <div>
    <GChart type="PieChart"
       :data="chartData"
       :options="chartOptions"
    />
  </div>
</template>

<script>
  export default{
    data() {
      return {

        chartData: [
          ['Fuel', 'Percentage'],
          ['biomass', 6.2],
          ['coal', 1.2],
          ['imports', 3.2],
          ['gas', 40.1],
        ],
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
