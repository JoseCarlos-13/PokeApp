<template>
  <div>
    <menubar></menubar>
    <iconsocial></iconsocial>
    <searchbar></searchbar>
    <pokeApi></pokeApi>
  </div>
</template>

<script>
import searchbar from './searchbar'
import menubar from './menubar'
import iconsocial from './iconsocial'
import pokeApi from './pokeApi'

export default {
  components: {
    'searchbar': searchbar,
    'menubar': menubar,
    'iconsocial': iconsocial,
    'pokeApi': pokeApi
  }
}
</script>

<style>
  body {
    color: white;
    background-color: red;
  }
</style>
