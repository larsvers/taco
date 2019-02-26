<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/taco-tree.jpeg">
    <h5>I want Tacos.</h5>
    <hello-world msg="Welcome to Your Taco.js App"/>
    <taco-graph :dataset="tacodata" name="mexican"></taco-graph>
    <taco-graph :dataset="burgerdata" name="burger"></taco-graph>
    <taco-graph :dataset="friesdata" name="fries"></taco-graph>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld';
import TacoGraph from './components/TacoGraph';

const d3 = Object.assign({}, require('d3-array'), require('d3-fetch'));

export default {
  name: 'app',
  components: {
    HelloWorld,
    TacoGraph,
  },
  data() {
    return {
      tacodata: [],
      burgerdata: [],
      friesdata: [],
    };
  },
  created() {
    const tacos = d3.csv('./tacodata.csv');
    const burgers = d3.csv('./burgerdata.csv');
    const fries = d3.csv('./friesdata.csv');

    Promise.all([tacos, burgers, fries]).then(res => {
      [this.tacodata, this.burgerdata, this.friesdata] = res;
    });
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
</style>
