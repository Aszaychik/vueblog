<template>
  <div>
    <!-- <div v-for="randomRef in randomRefs" :key="randomRef.id">
      <p>ID: {{ randomRef.value.id }}</p>
      <p>Title: {{ randomRef.value.title }}</p>
      <p>Body: {{ randomRef.value.body }}</p>
    </div> -->
    <PostList v-if="showPosts" :posts="posts" />
    <button @click="showPosts = !showPosts">Unmounted</button>
    <button @click="posts.pop()">Delete Post</button>
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
    // const posts = Array.from({ length: 10 }, () =>
    //   ref({
    //     id: Math.floor(Math.random() * 100),
    //     title: "Title " + Math.floor(Math.random() * 100),
    //     body:
    //       "Lorem ipsum dolor sit amet consectetur adipisicing elit. Vitae voluptatibus sint inventore ad tempore, possimus voluptatum nulla neque, quisquam maxime excepturi fugit! Asperiores mollitia nam laboriosam at quae quasi nesciunt? " +
    //       Math.floor(Math.random() * 100),
    //   })
    // );

    const posts = ref([
      {
        id: Math.floor(Math.random() * 100),
        title: "Title " + Math.floor(Math.random() * 100),
        body:
          "Lorem ipsum dolor sit amet consectetur adipisicing elit. Vitae voluptatibus sint inventore ad tempore, possimus voluptatum nulla neque, quisquam maxime excepturi fugit! Asperiores mollitia nam laboriosam at quae quasi nesciunt? " +
          Math.floor(Math.random() * 100),
      },
      {
        id: Math.floor(Math.random() * 100),
        title: "Title " + Math.floor(Math.random() * 100),
        body:
          "Lorem ipsum dolor sit amet consectetur adipisicing elit. Vitae voluptatibus sint inventore ad tempore, possimus voluptatum nulla neque, quisquam maxime excepturi fugit! Asperiores mollitia nam laboriosam at quae quasi nesciunt? " +
          Math.floor(Math.random() * 100),
      },
      {
        id: Math.floor(Math.random() * 100),
        title: "Title " + Math.floor(Math.random() * 100),
        body:
          "Lorem ipsum dolor sit amet consectetur adipisicing elit. Vitae voluptatibus sint inventore ad tempore, possimus voluptatum nulla neque, quisquam maxime excepturi fugit! Asperiores mollitia nam laboriosam at quae quasi nesciunt? " +
          Math.floor(Math.random() * 100),
      },
    ]);
    const showPosts = ref(true);

    return { posts, showPosts };
  },
};
</script>
