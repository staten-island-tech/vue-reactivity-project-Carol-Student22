<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <Main msg="Hi"/>
    <userName />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Main from './components/Main.vue'
import userName from './components/Name.vue'

export default {
  name: 'App',
  components: {
    Main,
    userName
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=VT323&display=swap');
* {
    font-family: 'VT323', monospace;
    font-size: 1.5rem;
}

/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
