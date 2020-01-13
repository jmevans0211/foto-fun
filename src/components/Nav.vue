<template>
  <div class="hello">
    <p>Foto Fun</p>
    <input />
    <button v-on:click='getData'>Search</button>
    <p>{{ test }}</p>
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
      test: 0,
    }
  },
  methods: {
    getData: function () {
      this.test +=1
    }
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
