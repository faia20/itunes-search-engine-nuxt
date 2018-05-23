<template>
  <div>
    <h1>Search iTunes</h1>
    <form @submit.prevent="submit">
      <input placeholder="Enter Artist Name" v-model="search" autofocus>
    </form>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        search: ''
      }
    },
    methods: {
      submit(event) {
        this.$router.push(`results/${this.search}`);
      }
    }
  }
</script>

<style>
  body {
    background: #f1f1f1;
  }
  h1 {
    padding: 20px;
    font-size: 1.3em;
    color: #444;
  }
</style>
