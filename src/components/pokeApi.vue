<template>
  <div class="pokeApi">
    <h1>{{pokemon.data.name}}</h1>
    <img v-bind:src="pokemon.data.sprites.front_default" alt="" width="350" height="350">
    <h3 style="font-family: 'Share Tech Mono', monospace;">abilities:</h3>
    <ul class="list-abilities">
      <li v-for="item in pokemon.data.abilities">{{item.ability.name}}</li>
    </ul>
  </div>
</template>

<script>
  import axios from 'axios'

export default {
  data(){
    return{
      pokemon: null
    }
  },

  mounted(){
    axios.get('https://pokeapi.co/api/v2/pokemon/pikachu/').then(response => (this.pokemon = response))
  }
}
</script>

<style>
  @import url('https://fonts.googleapis.com/css?family=Share+Tech+Mono');

  .pokeApi{
    color: white;
    margin-top: 50px;
  }

  h1{
    margin-top: 35px;
    font-family: 'Share Tech Mono', monospace;
  }

  .list-abilities li{
    list-style: none;
    color: darkblue;
    width: 300px;
    margin-left: 740px;
    background-color: yellow;
    border: solid 5px;
    border-color: darkblue;
    border-radius: 7px;
    padding: 15px;
  }

</style>
