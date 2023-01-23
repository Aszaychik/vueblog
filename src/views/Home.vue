<template>
  <div>
    <!-- <div v-for="randomRef in randomRefs" :key="randomRef.id">
      <p>ID: {{ randomRef.value.id }}</p>
      <p>Title: {{ randomRef.value.title }}</p>
      <p>Body: {{ randomRef.value.body }}</p>
    </div> -->
    <PostList :posts="posts" />
  </div>
</template>

<script>
import PostList from "../components/PostList.vue";
import { ref } from "vue";

export default {
  components: {
    PostList,
  },
  setup() {
    const posts = Array.from({ length: 10 }, () =>
      ref({
        id: Math.floor(Math.random() * 100),
        title: "Title " + Math.floor(Math.random() * 100),
        body: "Body " + Math.floor(Math.random() * 100),
      })
    );
    return { posts };
  },
};
</script>
