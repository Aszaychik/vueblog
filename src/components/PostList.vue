<template>
  <div>
    <div v-for="post in posts" :key="post.id">
      <p>ID: {{ post.value.id }}</p>
      <p>Title: {{ post.value.title }}</p>
      <p>Body: {{ post.value.body }}</p>
    </div>
  </div>
</template>

<script>
export default {
  props: ["posts"],
  setup(props) {
    console.log(props.posts);
    return {};
  },
};
</script>

<style lang="scss" scoped></style>
