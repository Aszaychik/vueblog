<template>
  <div class="home">
    <p ref="p">Hi my name is {{ name }}, and this is my number : {{ number }}</p>
    <button @click="handleClick">CLick!</button>
    <button @click="number++">Increment</button>
    <input type="text" v-model="name" />
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "HomeView",
  setup() {
    // const p = ref(null);
    const name = ref("AsZaychik");
    const number = ref("089519750202");

    const handleClick = () => {
      name.value = "Kayoko";
      number.value = "111001";
    };

    // const handleClick = () => {
    //   console.log(p, p.value);
    //   p.value.classList.add("paragraph");
    //   p.value.textContent = `This is your number : ${number}`;
    // };

    return { name, number, handleClick };
  },
};
</script>

<style scoped>
.paragraph {
  color: red;
}
</style>
