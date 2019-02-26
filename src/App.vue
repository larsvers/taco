<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/taco-tree.jpeg">
    <h5>I want Tacos.</h5>
    <hello-world msg="Welcome to Your Taco.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';

export default {
  name: 'app',
  components: {
    HelloWorld,
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

/* h5 {
  border: 1px solid tomato;
} */
</style>

<style scoped>
h5 {
  border: 1px solid tomato;
}
</style>
