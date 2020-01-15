<template>
  <div id="app">
    <Nav @searchInput="searchWithInput" />
    <PhotoContainer @fetchMoreImages="searchWithInput" v-bind:images="images" />
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
  },
  data() {
    return {
      images: null,
      input: ''
    }
  },
  methods: {
    searchWithInput: function (input, amount) {
      fetch(`https://api.unsplash.com/search/photos?client_id=2615908b6ad30256c4c37c49781519491cecc858f4782d2b06febb07fb3d347b&query=${input}&per_page=${amount}`)
        .then(response => response.json())
        .then(data => this.images = data.results)
        .then(this.input = input)
    },
    showMoreImages: function () {
      fetch(`https://api.unsplash.com/search/photos?client_id=2615908b6ad30256c4c37c49781519491cecc858f4782d2b06febb07fb3d347b&query=${this.input}&per_page=30`)
        .then(response => response.json())
        .then(data => this.images = data.results)
    }
  },
  mounted() {
    fetch('https://api.unsplash.com/search/photos?client_id=2615908b6ad30256c4c37c49781519491cecc858f4782d2b06febb07fb3d347b&query=fun&per_page=20')
      .then(response => response.json())
      .then(data => this.images = data.results)
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
