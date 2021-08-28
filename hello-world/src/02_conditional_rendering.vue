<template>
  <div>
    <h2 v-if="num === 0">The number is zero</h2>
    <h2 v-else-if="num < 0">The number is negative</h2>
    <h2 v-else-if="num > 0">The number is positive</h2>
    <h2 v-else>Not a number</h2>

    <!-- Mounts and unmounts dom node -->
    <template v-if="display">
      <h2>John Doe</h2>
      <h2>Codevolution</h2>
      <h2>Vue</h2>
    </template>

    <!-- toggles display css property -->
    <h2 v-show="showElement">Using v-show</h2>
  </div>
</template>

<script>
export default {
  name: "ConditionalRendering",
  data() {
    return {
      num: 1,
      display: true,
      showElement: false,
    };
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
