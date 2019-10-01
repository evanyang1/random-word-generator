<template>
  <div id="app">
    <RandomWord msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import RandomWord from './components/RandomWord.vue'

export default {
  name: 'app',
  components: {
    RandomWord
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
