<template>
  <div class="pokeapi">
    <input v-on:input="getPokemon()" v-model="query" placeholder="Enter your Pokemon here" />
    {{query}}
    {{currentPokemon}}
    <Abilities />
  </div>
</template>

<script>
import Abilities from './Abilities.vue'

export default {
  name: 'PokeApi',
  components: {
    Abilities
  },
  data () {
    return {
      query: '',
      currentPokemon: {}
    }
  },
  methods: {
    getPokemon: function() {
      console.log("Get Pokemon called");
    }
    
  }
}
</script>

<style scoped>

</style>
