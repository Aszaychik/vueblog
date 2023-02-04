<template>
  <div>
    <!-- <h2>ID: {{ post.value.id }}</h2> -->
    <h3>{{ post.title }}</h3>
    <p>{{ snippet }}</p>
  </div>
</template>

<script>
import { computed } from "vue";
export default {
  props: ["post"],
  setup(props) {
    const snippet = computed(() => {
      return props.post.body.substring(0, 100) + "...";
    });
    // console.log(props.post.value.body);
    return { snippet };
  },
};
</script>

<style lang="scss" scoped></style>
