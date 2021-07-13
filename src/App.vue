<template>
  <div id="app">
    <h1>Final de NT2 - Lucas Goldberg</h1>

    <Codificacion />
    
    <br>

  </div>
</template>

<script>
import Codificacion from './components/Codificacion.vue'

export default {
  name: 'App',
  components: {
    Codificacion
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
