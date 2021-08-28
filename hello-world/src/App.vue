<template>
  <div>
    <h2 v-for="(name, index) in names" :key="index">{{ index }} {{ name }}</h2>
    <h2 v-for="(name, index) in fullNames" :key="index">
      {{ name.first }} {{ name.last }}
    </h2>

    <div v-for="(actor, index) in actors" :key="index">
      <h2>{{ actor.name }}</h2>
      <h3 v-for="(movie, index) in actor.movies" :key="index">{{ movie }}</h3>
    </div>

    <h2 v-for="(value, key, index) in myInfo" :key="index">
      {{ index }} {{ key }} {{ value }}
    </h2>

    <template v-for="(name, index) in names" :key="index">
      <h2>{{ name }}</h2>
      <hr />
    </template>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      names: ["Bruce", "Clark", "Diana"],
      fullNames: [
        { first: "Bruce", last: "Wayne" },
        { first: "Clark", last: "Kent" },
        { first: "Princess", last: "Diana" },
      ],
      actors: [
        { name: "Christian Bale", movies: ["Batman", "The Prestige"] },
        { name: "Di Caprio", movies: ["Titanic", "Inception"] },
      ],
      myInfo: {
        name: "John Doe",
        channel: "Codevolution",
        course: "Vue 3",
      },
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
