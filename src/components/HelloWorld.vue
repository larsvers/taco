<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h5>I said, I want Tacos.</h5>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
