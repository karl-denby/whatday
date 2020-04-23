<template>
  <div id="app">
    <WhatDayIsIt v-bind:day=day />
  </div>
</template>

<script>
import WhatDayIsIt from './components/WhatDayIsIt.vue'

export default {
  name: 'App',
  components: {
    WhatDayIsIt
  },
  data () {
    return {
      day: null
    }
  },
  mounted () {
    this.getDay();
  },
  methods: {
    async getDay() {
      const api_url ="https://api.karldenby.com/dayofweek";
      console.log(`Using the url: ${api_url}`)
      const res = await fetch(api_url)
      const data = await res.json();
      console.log(`Data returned is ${data.day}`)
      this.day = data.day;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
