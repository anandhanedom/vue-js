<template>
  <div>
    <h2>{{ name }}</h2>
    <div>
      <!-- <button v-on:click="name = 'Batman'">Change name</button> -->
      <h2>{{ count }}</h2>
      <div>
        <!-- <button v-on:click="increment(1)">Increment 1</button> -->

        <button @click="changeName($event), increment(1, $event)">
          Change name
        </button>

        <button @click="increment(1, $event)">Increment 1</button>
        <button @click="decrement(1)">Decrement 1</button>
        <button @click="increment(5)">Increment 5</button>
        <button @click="decrement(5)">Decrement 5</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "EventHandling",
  data() {
    return {
      name: "John Doe",
      count: 0,
    };
  },
  methods: {
    increment(num, event) {
      this.count += num;
      console.log(event);
    },
    decrement(num) {
      this.count -= num;
    },
    changeName(e) {
      console.log(e);
      this.name = "batman";
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
