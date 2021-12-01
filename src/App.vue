<template>
  <div id="app">
    <Nav/>
    <Movies/>
    <h1>Ciao</h1>
  </div>
</template>

<script>
import Nav from './components/Nav.vue';
import Movies from './components/Movies.vue'

export default {
  name: 'App',
  components: {
    Nav,
    Movies
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
