<template lang="html">
  <div>
    <ul>
      <list-beer v-for="(beer, index) in beers"
    :beer="beer" :key="index"></list-beer>
     </ul>
  </div>
</template>

<script>
import ListComponent from './ListComponent.vue';

export default {
  name: 'beers-list',
  props: ['beers'],
  components: {
    "list-beer": ListComponent
  }
}
</script>

<style lang="css" scoped>
</style>
