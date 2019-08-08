<template>
  <div id="app">
    <p>Generation Analysis</p>
    <generation-list :data='data'></generation-list>
  </div>
</template>

<script>
import GenerationList from './components/GenerationList.vue'

export default {
  name: 'app',
  data(){
    return {
      data: []
    };
  },
  components: {
    "generation-list": GenerationList
  },

mounted(){
  fetch('https://api.carbonintensity.org.uk/generation')
  .then(res => res.json())
  .then(data => this.data = data)
}
}



</script>

<style>

</style>
