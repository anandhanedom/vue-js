<template>
  <div>
    <input type="text" ref="inputRef" />
    <PostList ref="postListRef" />
  </div>
</template>

<script>
import PostList from "./PostList.vue";

export default {
  components: { PostList },
  name: "TemplateRef",
  mounted() {
    console.log(this.$refs.postListRef)
    this.$refs.inputRef.focus();
  },
  data() {
    return {};
  },
};
</script>

<style scoped></style>
