<template>
  <div>
    <form @submit.prevent="createPost">
      <div>
        <label for="userId">Post user id</label>
        <input type="text" id="userId" v-model="formData.userId" />
      </div>
      <div>
        <label for="title">Post title</label>
        <input type="text" id="title" v-model="formData.title" />
      </div>
      <div>
        <label for="body">Post body</label>
        <input type="text" id="body" v-model="formData.body" />
      </div>
      <button>Create Post</button>
    </form>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "CreatePost",
  data() {
    return {
      formData: {
        userId: "",
        title: "",
        body: "",
      },
    };
  },
  methods: {
    async createPost() {
      try {
        const res = await axios.post(
          "https:/jsonplaceholder.typicode.com/posts",
          this.formData
        );

        console.log(res.data);
      } catch (error) {
        console.log(error);
      }
    },
  },
};
</script>

<style scoped></style>
