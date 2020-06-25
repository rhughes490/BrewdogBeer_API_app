<template lang="html">
<div>
  <beer-list :beers="beers"></beer-list>
  <beer-detail :selectedBeer="selectedBeer"></beer-detail>
</div>
</template>

<script>
import { eventBus } from './main.js'
import BeerDetail from './components/BeerDetails.vue'
import BeerList from './components/BeerList.vue'

export default {
  name: 'App',
    data(){
    return {
      beers: [],
      selectedBeer: null
    }
  },
  components: {
    'beer-list': BeerList,
    'beer-detail': BeerDetail
  },
  mounted() {
    fetch('https://api.punkapi.com/v2/beers')
    .then(response => response.json())
    .then(data => this.beers = data)

    eventBus.$on('selected-beer', (beer) => {
      this.selectedBeer = beer
    })
  }
 }


</script>

<style lang="css" scoped>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
