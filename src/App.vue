<template>
  <div>
    <h1>Brewdog Beers</h1>
    <div id="main-container">
      <!-- <beers-list :beers='beers' /> -->
      <beer-select class="beer-select" :beers='beers'/>
      <beer-detail class="beer-detail" :beer='selectedBeer' />
    </div>
  </div>
</template>

<script>
import BeersList from './components/BeersList.vue';
import { eventBus } from './main.js';
import BeerDetail from './components/BeerDetail.vue';
import BeerSelect from './components/BeerSelect.vue';

export default {
  name: 'app',
  data() {
    return {
      beers: [],
      selectedBeer: null
    };
  },
  mounted() {
    fetch('https://api.punkapi.com/v2/beers')
    .then(response => response.json())
    .then(beers => this.beers = beers)

    eventBus.$on('beer-selected', (beer) => {
      this.selectedBeer = beer;
    })
  },
  components: {
    "beers-list": BeersList,
    "beer-detail": BeerDetail,
    "beer-select": BeerSelect
  }
}
</script>

<style>
  #main-container {
    display: flex;
    flex-direction: column;
  }

  .beer-select {
    justify-content: center;
    align-self: center;
  }

  .beer-detail {

  }
</style>
