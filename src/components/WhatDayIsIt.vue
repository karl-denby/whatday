<template>
  <div class="day">
    <h1>{{ day }}</h1>
  </div>
</template>

<script>
export default {
  name: 'WhatDayIsIt',
  props: {
    day: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  margin: 40px 0 0;
}
</style>
