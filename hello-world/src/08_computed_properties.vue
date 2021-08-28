<template>
  <div>
    <h2>Computed fullname - {{ fullName }}</h2>
    <button @click="changeFullname">Change fullname</button>
    <button @click="items.push({ id: 4, title: 'Keyboard', price: 50 })">
      Add item
    </button>
    <h2>Total - {{ getTotal }}</h2>
  </div>
</template>

<script>
export default {
  name: "ComputedProperties",
  data() {
    return {
      firstName: "Bruce",
      lastName: "Wayne",
      items: [
        { id: 1, title: "TV", price: 100 },
        { id: 2, title: "Phone", price: 200 },
        { id: 3, title: "Laptop", price: 300 },
      ],
    };
  },
  methods: {
    changeFullname() {
      this.fullName = "Clark Kent";
    },
  },
  computed: {
    fullName: {
      get() {
        return `${this.firstName} ${this.lastName}`;
      },
      set(value) {
        const names = value.split(" ");
        this.firstName = names[0];
        this.lastName = names[1];
      },
    },
    getTotal() {
      return this.items.reduce((total, curr) => (total += curr.price), 0);
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
