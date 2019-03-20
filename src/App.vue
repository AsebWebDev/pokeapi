<template>
  <div id="app">
    <h1>Poke-API</h1>
    <PokeApi />
  </div>
</template>

<script>
import PokeApi from './components/PokeApi.vue'

export default {
  name: 'app',
  components: {
    PokeApi
  }
}
</script>

<style>

  h1 {
    color: white;
  }

  body {
    margin: 0;
    padding: 0;
    background-image: url(../public/bg.jpg);
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    background-attachment:fixed;
  }

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;

  }
</style>
