<template>
  <div class="nav">
    <h1>Foto<span>Finder</span></h1>
    <div>
      <input v-model.lazy="input"/>
      <button v-on:click="getData">Search</button>
      <p v-if="errorMessage">Please enter something into your search input</p>
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
  }
}
</script>

<style scoped>
  h1 {
    font-size: 85px;
    margin-bottom: 20px;
  }
  h1 span {
    color: #f72a57;
  }
  .nav div {
    height: 50px;
    margin-bottom: 50px
  }
  input {
    color: #f72a57;
    font-size: 20px;
    height: 100%;
    outline: none; 
    padding-left: 6px;
    margin-right: 5px;
    width: 20%;
  }
  button {
    background-color: #f72a57;
    color: whitesmoke;
    font-size: 30px;
    height: 111%;
    margin-left: 5px;
    outline: none; 
    transform: translateY(5%);
    width: 20%;
  }
</style>
