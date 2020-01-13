<template>
  <div>
    <img v-for="(image, index) in images" :key="index" :src="image.urls.small"/>
  </div>
</template>

<script>
export default {
  name: 'PhotoContainer',
  props: {
    msg: String
  },
  data() {
    return {
      images: null,
      }
  },
  mounted() {
    fetch('https://api.unsplash.com/search/photos?client_id=2615908b6ad30256c4c37c49781519491cecc858f4782d2b06febb07fb3d347b&query=fun')
      .then(response => response.json())
      .then(data => this.images = data.results)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
