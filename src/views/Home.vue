<template>
  <div class="home">
    <h1>Home</h1>
    <input type="text" v-model="search" />
    <button @click="handleClick">Stop</button>
    <div v-for="(name, index) in resultSearch" :key="index">
      {{ name }}
    </div>
  </div>
</template>

<script>
import { computed, ref, watch, watchEffect } from "vue";
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

    const stop = watch(search, () => {
      console.log(`Watch!`);
    });

    const stopEffect = watchEffect(() => {
      console.log(`WatchEffect!`, search.value);
    });

    const handleClick = () => {
      stop();
      stopEffect();
    };

    const resultSearch = computed(() => {
      return names.value.filter((name) => name.includes(search.value));
    });

    return { search, names, resultSearch, handleClick };
  },
};
</script>
