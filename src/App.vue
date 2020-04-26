<template>
  <div id="app">
    <TacoBox title="Welcome to Taco Land! 🌮"/>
  </div>
</template>

<script>
import TacoBox from './components/TacoBox.vue'

export default {
  name: 'App',
  components: {
    TacoBox
  }
}
</script>

<style>
body {
  background-color: #051A35;
}

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #A3D7CD;
  margin-top: 60px;
}
</style>
