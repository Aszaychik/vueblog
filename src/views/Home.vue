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
        body:
          "Lorem ipsum dolor sit amet consectetur adipisicing elit. Vitae voluptatibus sint inventore ad tempore, possimus voluptatum nulla neque, quisquam maxime excepturi fugit! Asperiores mollitia nam laboriosam at quae quasi nesciunt? " +
          Math.floor(Math.random() * 100),
      })
    );

    return { posts };
  },
};
</script>
