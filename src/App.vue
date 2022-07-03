<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <Header_vue></Header_vue>
    <Modal_vue></Modal_vue>
    <Footer_vue></Footer_vue>

  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Header_vue from './components/Header.vue'
import Modal_vue from './components/Modal.vue'
import Footer_vue from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld,
    Header_vue,
    Modal_vue,
    Footer_vue
  }
}
</script>

<style>
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px; */
}
</style>
