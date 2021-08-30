<template>
  <h3>Appcomponent USERNAME : {{ name }}</h3>
  <ComponentC />
</template>

<script>
import ComponentC from "./components/ComponentC.vue";

export default {
  name: "App",
  components: {
    ComponentC,
  },
  data() {
    return {
      name: "johndoe",
    };
  },
  // provide: {
  //   username: "johndoe",
  // },
  provide() {
    return { username: this.name };
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
