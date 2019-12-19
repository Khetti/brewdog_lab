<template lang="html">
  <li>{{beer.name}}</li>
</template>

<script>
export default {
  name: 'list-beer',
  props: ['beer']
}
</script>

<style lang="css" scoped>
</style>
