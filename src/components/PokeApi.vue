<template>
  <div class="pokeapi">
    <input v-on:input="getPokemon()" v-model="query" placeholder="Enter your Pokemon here" />
    {{query}}
    <Abilities v-if="pokemon" v-bind:pokemon="pokemon" />
    <h1 v-else>No Pokemon found yet...</h1>
  </div>
</template>

<script>
import Abilities from './Abilities.vue'
import axios from 'axios';

export default {
  name: 'PokeApi',
  components: {
    Abilities
  },
  data () {
    return {
      query: '',
      pokemon: null
    }
  },
  methods: {
    getPokemon: function() {
      axios
        .get('https://pokeapi.co/api/v2/pokemon/'+this.query)
        .then(response => {
          console.log(response.data);
          this.pokemon = response.data;
        })
        .catch(error => {
          this.pokemon = null;
          if (error.response.status === 404) console.log("Pokemon does not exist.")
        });
    }
  }
}
</script>

<style scoped>

</style>
