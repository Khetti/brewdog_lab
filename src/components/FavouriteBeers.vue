<template lang="html">
  <input type="button" value="Add Favourite" v-on:click="handleClick" />
</template>

<script>
import { eventBus } from '../main.js';

export default {
  name: 'favourite-beers',
  props: ['beer'],
  methods: {
    handleClick(){
      console.log("Favourite Button Clicked");
    }
  }
}
</script>

<style lang="css" scoped>
</style>
