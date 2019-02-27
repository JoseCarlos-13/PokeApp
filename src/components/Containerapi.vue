<template>
  <div class="container">
    <searchbar :getPokemon="getPokemon"></searchbar>
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
      pokemonReceived: null,
      pokelink: null
    }
  },

  methods: {
    getPokemon (search) {
      axios.get('https://pokeapi.co/api/v2/pokemon/' + search).then(response => (this.pokemonReceived = response))
      axios.get('https://www.google.com/search?ei=16Z2XJ2_Nfiu5OUPvdqksAQ&q=pikachu&oq=pikachu&gs_l=psy-ab.3..0i67j0j0i131i67l2j0i131l2j0i67j0l3.371419.372711..373087...1.0..0.217.1274.0j5j2......0....1..gws-wiz.....6..0i71j35i39.TQvD99CaPA4').then(response => (this.pokelink = response))
    }
  },

  mounted () {
    this.getPokemon("pikachu")
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
    margin-left: 170px;
  }

</style>
