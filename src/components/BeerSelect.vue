<template lang="html">
  <select v-on:change="handleSelect" v-model="selectedBeer">

  <option v-for="(beer, index) in beers" :key="index" :value="beer">{{beer.name}}</option>
  </select>

</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'beer-select',
  props: ['beers'],
  data() {
    return {
      selectedBeer: null
    }
  },
  methods: {
    handleSelect() {
      eventBus.$emit('beer-selected', this.selectedBeer)
    }
  }
  }
</script>

<style lang="css" scoped>
</style>
