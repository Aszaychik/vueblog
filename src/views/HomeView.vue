<template>
  <div class="home">
    <p ref="p">Hi {{ name }},</p>
    <button @click="handleClick">Show Number!</button>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "HomeView",
  setup() {
    const p = ref(null);
    const name = "AsZaychik";
    const number = "089519750202";

    const handleClick = () => {
      console.log(p, p.value);
      p.value.classList.add("paragraph");
      p.value.textContent = `This is your number : ${number}`;
    };

    return { name, number, p, handleClick };
  },
};
</script>

<style scoped>
.paragraph {
  color: red;
}
</style>
