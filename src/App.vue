<template>
<body>
  <div id="app">
    <Game msg />
  </div>
</body>
</template>

<script>
import Game from './components/game.vue'

export default {
  name: 'app',
  components: {
    Game
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  padding: 3em;
}
body { 
  background: url("./assets/img/bg.gif") no-repeat center center fixed; 
  -webkit-background-size: cover;
  -moz-background-size: cover;
  -o-background-size: cover;
  background-size: cover;
}
</style>
