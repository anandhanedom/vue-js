<template>
  <div>
    <button @click="getPosts">Load Post</button>
    <h3 v-if="errorMessage">{{ errorMessage }}</h3>
    <div v-for="post in posts" :key="post.id">
      <h3>{{ post.id }} {{ post.title }}</h3>
      <p>{{ post.body }}</p>
      <hr />
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "PostList",
  data() {
    return {
      posts: [],
      errorMessage: "",
    };
  },
  methods: {
    async getPosts() {
      try {
        const res = await axios.get(
          "https:/jsonplaceholder.typicode.com/posts"
        );

        this.posts = res.data;
      } catch (error) {
        this.errorMessage = "Error retrieving data";
      }
    },
  },
};
</script>

<style scoped></style>
