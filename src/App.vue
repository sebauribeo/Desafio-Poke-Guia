<template>
  <div id="app">
    <PokeGuia/>
  </div>
</template>

<script>
import PokeGuia from './components/PokeGuia.vue'

export default {
  name: 'App',
  components: {
    PokeGuia
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
