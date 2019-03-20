<template>
  <div class="abilities">
    <h1>Abilities of {{pokemon.name.toUpperCase()}}</h1>
    <ul>
      <li v-bind:key="i" v-for="(ability,i) in pokemon.abilities">{{ability.ability.name}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Abilities',
  props: {
    pokemon: Object
  },
}
</script>

<style scoped>

</style>
