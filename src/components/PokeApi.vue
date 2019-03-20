<template>
  <div class="pokeapi jumbotron">
    <div class="left">
      <img src="../assets/pikatchu.gif" alt="">
    </div>
    <div class="center">
      <input v-on:input="getPokemon()" v-model="query" placeholder="Enter your Pokemon here..." />
      <p>Searching for {{query}}</p>
      <Abilities v-if="pokemon" v-bind:pokemon="pokemon" />
      <h4 v-else>No Pokemon found yet...</h4>
    </div>
    <div class="right">
      <img src="../assets/pikatchu2.gif" alt="">
    </div>
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
  // mounted() {
  //   if (localStorage.getItem('storage')) {
  //     try {
  //       this.storage = JSON.parse(localStorage.getItem('storage'));
  //     } catch(e) {
  //       localStorage.removeItem('storage');
  //     }
  //   }
  // },
  methods: {
    getPokemon: function () {
      if (this.query === '') this.pokemon = null
      else {
        axios
          .get('https://pokeapi.co/api/v2/pokemon/'+this.query)
          .then(response => {
            this.pokemon = response.data;
          })
          .catch(error => {
            this.pokemon = null;
            if (error.response.status === 404) console.log("Pokemon does not exist.")
          });
      }  
    }
  }
}
</script>

<style scoped>
  img { width: 100px; }

  input { width: 200px; }

  .pokeapi {
    display: flex;
    flex-direction: row;
    justify-content: center;
  }
</style>
