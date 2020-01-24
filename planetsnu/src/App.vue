<template>
  <div id="app">
   <CodingChallenge msg="initial commit" />
  </div>
</template>

<script>
import CodingChallenge from './components/CodingChallenge.vue'

export default {
  name: 'app',
  components: {
    CodingChallenge
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
