<template>
  <div class="nav">
    <p>Foto Fun</p>
    <input />
    <button v-on:click='getData'>Search</button>
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
      log: 'in data object',
    }
  },
  methods: {
    getData: function () {
      this.$emit('searchInput')
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
