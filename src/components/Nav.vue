<template>
  <div class="nav">
    <p>Foto Fun</p>
    <input v-model.lazy="input"/>
    <button v-on:click="getData">Search</button>
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
    }
  },
  methods: {
    getData: function () {
      this.$emit('searchInput', this.input)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .nav {
    font-size: 40px;
  }
</style>
