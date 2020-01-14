<template>
  <div class="nav">
    <h1>Foto<span>Finder</span></h1>
    <div>
      <input v-model.lazy="input"/>
      <button v-on:click="getData">Search</button>
      <p v-if="errorMessage">Please enter something into your search input</p>
    </div>
    <div>
      <button v-on:click="increaseImageAmount">+</button>
      <p>{{this.imageAmount}}</p>
      <button v-on:click="decreaseImageAmount">-</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Nav',
  props: {
    msg: String
  },
  data () {
    return {
      input: '',
      imageAmount: 20,
      errorMessage: false
    }
  },
  methods: {
    getData: function () {
      if (this.input === '') {
        this.errorMessage = true
      } else {
        this.errorMessage = false
        this.$emit('searchInput', this.input, this.imageAmount)
      }
    },
    increaseImageAmount: function () {
      if (this.imageAmount < 30) {
        this.imageAmount += 5
      }
    },
    decreaseImageAmount: function () {
      if (this.imageAmount >= 10) {
        this.imageAmount -= 5
      }
    }  
  }
}
</script>

<style scoped>
  .nav {
    font-size: 40px;
  }
</style>
