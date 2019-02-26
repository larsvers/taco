<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h5>I said, I want {{ thing }}.</h5>
    <h5>or was it {{ reversedThing }}?</h5>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  data() {
    return {
      thing: 'Tacos',
    };
  },
  computed: {
    reversedThing() {
      return this.thing
        .split('')
        .reverse()
        .join('');
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
