<template>
  <div>
    <!-- <Card></Card>
    <Card>Card content 1</Card>
    <Card>
      <h2>Card content 2</h2>
    </Card>
    <Card>
      <img src="https://picsum.photos/200" alt="" />
    </Card>
    <Card>
      <template v-slot:header>
        <h3>Header</h3>
      </template>
      <template v-slot:default>
        <img src="https://picsum.photos/200" alt="" />
      </template>
      <template v-slot:footer>
        <button>View details</button>
      </template>
    </Card> -->

    <NamesList>
      <template v-slot:default="slotProps">
        {{ slotProps.firstName }}, {{ slotProps.lastName }}
      </template>
    </NamesList>
    <NamesList>
      <template v-slot:default="slotProps">
        {{ slotProps.lastName }}, {{ slotProps.firstName }}
      </template>
    </NamesList>
    <NamesList>
      <template v-slot:default="slotProps">
        {{ slotProps.firstName }}
      </template>
    </NamesList>
  </div>
</template>

<script>
// import Card from "./components/Card.vue";
import NamesList from "./components/NamesList.vue";

export default {
  name: "App",
  components: {
    // Card,
    NamesList,
  },
  data() {
    return {};
  },
  methods: {},
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
