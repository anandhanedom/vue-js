<template>
  <div>
    <!-- <Greet name="Bruce" heroName="Batman" />
    <Greet name="Clark" heroName="Superman" />
    <Greet :name="name" :heroName="channel" /> -->

    <Article
      title="Article title"
      :likes="50"
      :isPublished="true"
      id="my-article"
    />
  </div>
</template>

<script>
// import Greet from "./components/Greet.vue";
import Article from "./components/Article.vue";

export default {
  name: "App",
  components: {
    // Greet,
    Article,
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
