<template lang="html">
<div>
  <li v-on:click="handleClick">{{beer.name}}</li>
</div>
</template>

<script>
import {eventBus} from '../main.js'

export default {
  props: ['beer'],
  methods: {
    handleClick: function () {
      eventBus.$emit('selected-beer', this.beer)
    }
  }
}
</script>

<style>

</style>
