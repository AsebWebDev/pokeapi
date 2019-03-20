<template>
  <div class="abilities">
    <h4>Abilities of {{pokemon.name}}</h4>
    <ul class="list-group">
      <li class="list-group-item" v-bind:key="i" v-for="(ability,i) in pokemon.abilities">{{ability.ability.name}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Abilities',
  props: { pokemon: Object },
}
</script>

<style scoped>
  .abilities { width: 200px; }
</style>
