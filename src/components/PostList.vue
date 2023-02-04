<template>
  <div>
    <div v-for="post in posts" :key="post.id">
      <!-- <p>ID: {{ post.value.id }}</p>
      <p>Title: {{ post.value.title }}</p>
      <p>Body: {{ post.value.body }}</p> -->
      <PostSingle :post="post" />
    </div>
  </div>
</template>

<script>
import PostSingle from "./PostSingle.vue";

export default {
  components: {
    PostSingle,
  },
  props: ["posts"],
  setup(props) {
    console.log(props.posts);
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
