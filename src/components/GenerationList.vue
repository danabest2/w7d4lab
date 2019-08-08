<template>
  <div class="GenerationList">
    <p>generation title</p>
    <p>{{data}}</p>
    <p>{{chartData}}</p>
  </div>
</template>

<script>
export default {
  name: 'GenerationList',
  props: ['data', 'chartData']
}
</script>


<style scoped>

</style>
