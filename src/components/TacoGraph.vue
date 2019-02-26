<template>
  <div>
    <div class="graph-wrap">
      <svg height="110">
        <g v-for="(row, index) in dataset" :key="index">
          <rect :y="index * 30" :width="+row.sales" height="20"></rect>
          <text :y="index * 30" :x="3" dy="0.15em">{{row.product}}</text>
        </g>
      </svg>
      <div class="graph-name">{{name}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TacoGraph',
  props: {
    dataset: Array,
    name: String,
  },
};
</script>

<style scoped>
.graph-wrap {
  position: relative;
  display: inline-block;
  background: #f5f5a8;
  padding: 1em;
  margin: 1em;
}

text {
  fill: white;
  text-anchor: start;
  dominant-baseline: hanging;
}

.graph-name {
  position: absolute;
  bottom: 0;
  right: 0;
  padding: 0.2em 0.8em;
  color: #aaa;
}
</style>
