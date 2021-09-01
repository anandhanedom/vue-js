<template>
  <div>
    <h3 v-for="(name, index) in names" :key="index">
      <slot :firstName="name.firstName" :lastName="name.lastName"></slot>
    </h3>
  </div>
</template>

<script>
export default {
  name: "NamesList",
  data() {
    return {
      names: [
        { firstName: "Bruce", lastName: "Wayne" },
        { firstName: "Clark", lastName: "Kent" },
        { firstName: "Princess", lastName: "Diana" },
      ],
    };
  },
};
</script>

<style scoped></style>
