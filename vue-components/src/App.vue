<template>
  <div>
    <Greet name="Bruce" heroName="Batman" />
    <Greet name="Clark" heroName="Superman" />
    <Greet :name="name" :heroName="channel" />
  </div>
</template>

<script>
import Greet from "./components/Greet.vue";

export default {
  name: "App",
  components: {
    Greet,
  },
  data() {
    return {
      name: "John Doe",
      channel: "Codevolution",
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
