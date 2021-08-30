<template>
  <!-- Immediate and deep watchers -->
  <div>
    <h2>Volume tracker (0-20)</h2>
    <h3>Current volume : {{ volume }}</h3>
    <div>
      <button @click="volume += 2">Increase</button>
      <button @click="volume -= 2">Decrease</button>
    </div>
    <div>
      <input type="text" v-model="movie" />
      <input type="text" v-model="movieInfo.title" />
      <input type="text" v-model="movieInfo.actor" />
    </div>
    <div>
      <button @click="movieList.push('Wonder Woman')">Add movie</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "Watchers",
  data() {
    return {
      volume: 0,
      movie: "Batman",
      movieInfo: {
        title: "",
        actor: "",
      },
      movieList: ["Batman", "Superman"],
    };
  },
  methods: {},
  computed: {},
  watch: {
    volume(newValue, oldValue) {
      if (newValue > oldValue && newValue === 16) {
        alert(
          "Listening to a high volume for a long time may damage your hearing"
        );
      }
    },
    // movie(newValue) {
    //   console.log(`Calling API with movie name = ${newValue}`);
    // },
    movie: {
      handler(newValue) {
        console.log(`Calling API with movie name = ${newValue}`); // Will be called on page load as well
      },
      immediate: true,
    },
    movieInfo: {
      handler(newValue) {
        console.log(
          `Calling API with movie title = ${newValue.title}, and actor = ${newValue.actor}`
        );
      },

      deep: true, //watch for objects when mutating
    },

    movieList: {
      handler(newValue) {
        console.log(`Updated list ${newValue}`);
      },

      deep: true, //watch for array when mutating
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
