<template>
  <div>
    <h2>{{ 2 + 3 + 5 }}</h2>
    <h2>{{ 5 + 10 + 15 }}</h2>
    <h2>Add method - {{ add(2, 3, 5) }}</h2>
    <h2>Add method - {{ add(10, 15, 20) }}</h2>
    <h2>Multiply method - {{ multiply(baseValue) }}</h2>
  </div>
</template>

<script>
export default {
  name: "Methods",
  data() {
    return {
      baseMultiplier: 5,
      baseValue: 2,
    };
  },
  methods: {
    add(x, y, z) {
      return x + y + z;
    },
    multiply(num) {
      return num * this.baseMultiplier;
    },
  },
};
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
