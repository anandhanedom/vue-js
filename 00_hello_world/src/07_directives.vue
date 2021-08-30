<template>
  <!-- Directives : v-once, v-pre -->
  <div>
    <h2 v-once>{{ name }}</h2>
    <button @click="name = 'Batman'">Change name</button>
    <h2 v-pre>{{ name }}</h2>
  </div>
</template>

<script>
export default {
  name: "Directives",
  data() {
    return {
      name: "John Doe",
    };
  },
  methods: {},
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
