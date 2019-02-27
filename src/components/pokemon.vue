<template>
  <div v-if="pokemon" class="pokemon">
    <h1>{{pokemon.data.name}}</h1>
    <img v-bind:src="pokemon.data.sprites.front_default" alt="" width="350" height="350">
    <h3 style="font-family: 'Press Start 2P', cursive;">abilities:</h3>
    <ul class="list-abilities">
      <li :key="item.index" v-for="item in pokemon.data.abilities">{{item.ability.name}}</li>
    </ul>
    <a style="color: white;" :href="pokelink" target="_blank">click here for more informations about this pokemon</a>
  </div>
</template>

<script>

export default {
  data () {
    return {
      pokelink: null
    }
  },

  updated () {
    this.pokelink = 'https://www.google.com/search?q=' + this.pokemon.data.name
  },

  props: ['pokemon']

}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Press+Start+2P');

  .pokeApi{
    color: white;
    margin-top: 50px;
  }

  h1{
    margin-top: 35px;
    font-family: 'Press Start 2P', cursive;
  }

  .list-abilities li{
    list-style: none;
    color: darkblue;
    width: 300px;
    margin-left: 546px;
    background-color: yellow;
    border: solid 5px;
    border-color: darkblue;
    border-radius: 7px;
    padding: 15px;
  }

  .list-abilities{
    margin-bottom: 26px;
  }

</style>
