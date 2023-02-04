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
import { onMounted, onUnmounted, onUpdated } from "vue";

export default {
  components: {
    PostSingle,
  },
  props: ["posts"],
  setup(props) {
    onMounted(() => console.log(`Component Mounted`));

    onUnmounted(() => console.log(`Component onUnmounted`));

    onUpdated(() => console.log(`Component onUpdated`));
  },
};
</script>

<style lang="scss" scoped></style>
