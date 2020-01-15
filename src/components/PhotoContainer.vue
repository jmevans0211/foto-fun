<template>
  <div>
    <div class="div__image--container">
      <p v-if="images.length === 0">🧐Hmm, we aren't finding any images related to that search.</p>
      <img v-for="(image, index) in this.images" :key="index" :src="image.urls.small"/>
    </div>
  <button v-on:click="viewMoreImages">View More Images</button>
  </div>
</template>

<script>
export default {
  name: 'PhotoContainer',
  props: {
    images: Array
  },
  methods: {
    viewMoreImages: function () {
      this.$emit('fetchMoreImages', 30)
    }
  }
}
</script>

<style scoped>
.div__image--container {
  column-count: 3;
  column-gap: 2%
}

img {
  display: inline-block;
  padding: 10px
}

</style>
