<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search" />
    <div v-for="(name, index) in resultSearch" :key="index">
      {{ name }}
    </div>
  </div>
</template>

<script>
import { computed, ref } from "vue";
export default {
  name: "Home",
  setup() {
    // const name = computed(() => {
    //   return "AsZaychik";
    // });

    const search = ref("");

    const names = ref([
      "Emily",
      "Michael",
      "Madison",
      "Matthew",
      "Daniel",
      "Jessica",
      "Nicholas",
      "Ashley",
      "Sarah",
      "Brandon",
      "Alyssa",
      "Jacob",
      "Samantha",
      "William",
      "Jennifer",
      "Joseph",
      "Amanda",
      "Joshua",
      "Stephanie",
      "Andrew",
      "Lauren",
      "David",
      "Rachel",
      "Anthony",
    ]);

    const resultSearch = computed(() => {
      return names.value.filter((name) => name.includes(search.value));
    });

    return { search, names, resultSearch };
  },
};
</script>
