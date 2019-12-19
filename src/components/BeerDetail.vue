<template lang="html">
  <div v-if="beer">
    <h3>{{ beer.name }}</h3>
    <p>{{ beer.tagline }}</p>
    <p>Description: {{ beer.description }}</p>
    <p>ABV: {{ beer.abv }}%</p>
    <favourite-beers :beer="beer" :key="index"></favourite-beers>
  </div>
</template>

<script>
import FavouriteBeers from './components/FavouriteBeers.vue';

export default {
  name: 'beer-detail',
  props: ['beer'],
  components: {
    "favourite-beers": FavouriteBeers
  }
}
</script>

<style lang="css" scoped>

</style>
