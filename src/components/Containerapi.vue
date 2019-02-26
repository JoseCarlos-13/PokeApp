<template>
  <div class="container">
    <searchbar></searchbar>
    <pokemon :pokemon="pokemonReceived"></pokemon>
  </div>
</template>

<script>
import searchbar from './searchbar'
import pokemon from './pokemon'
import axios from 'axios'

export default {
  components: {
    'searchbar': searchbar,
    'pokemon': pokemon
  },

  data () {
    return {
      pokemonReceived: null
    }
  },

  methods: {
    getPokemon () {
      axios.get('https://pokeapi.co/api/v2/pokemon/pikachu/').then(response => (this.pokemonReceived = response))
    }
  },

  mounted () {
    this.getPokemon()
  }
}
</script>

<style>
  .container{
    color: white;
    background-color: darkblue;
    margin-top: 15px;
    padding: 15px;
    border-radius: 30px;
    width: 1520px;
    margin-left: 164px;
  }

</style>
