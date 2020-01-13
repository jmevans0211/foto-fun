<template>
  <div id="app">
    <Nav msg="Welcome to Your Vue.js App"/>
    <PhotoContainer />
  </div>
</template>

<script>
import Nav from './components/Nav.vue'
import PhotoContainer from './components/PhotoContainer'

export default {
  name: 'app',
  components: {
    Nav,
    PhotoContainer
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
