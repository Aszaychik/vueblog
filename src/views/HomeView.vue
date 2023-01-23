<template>
  <div class="home">
    <h2>Ref</h2>
    <p ref="p">Hi my name is {{ contactOne.name }}, and this is my number : {{ contactOne.number }}</p>
    <button @click="handleClick">CLick!</button>
    <button @click="contactOne.number++">Increment</button>
    <input type="text" v-model="contactOne.name" />

    <h2>Reactive</h2>
    <p ref="p">Hi my name is {{ contactTwo.name }}, and this is my number : {{ contactTwo.number }}</p>
    <button @click="handleClick2">CLick!</button>
    <button @click="contactTwo.number++">Increment</button>
    <input type="text" v-model="contactTwo.name" />
  </div>
</template>

<script>
import { ref, reactive } from "vue";

export default {
  name: "HomeView",
  setup() {
    // const p = ref(null);
    // const name = ref("AsZaychik");
    // const number = ref("089519750202");
    const contactOne = ref({ name: "AsZaychik", number: "089519750202" });
    const contactTwo = reactive({ name: "Yuuka", number: "129472147214" });

    // const handleClick = () => {
    //   name.value =wekjrhwkrhw "Kayoko";
    //   number.value = "111001";
    // };

    const handleClick = () => {
      contactOne.value.name = "Kayoko";
      contactOne.value.number = "111001";
    };
    const handleClick2 = () => {
      contactTwo.name = "Noa";
      contactTwo.number = "1947912471927";
    };

    // const handleClick = () => {
    //   console.log(p, p.value);
    //   p.value.classList.add("paragraph");
    //   p.value.textContent = `This is your number : ${number}`;
    // };

    return { contactOne, contactTwo, handleClick, handleClick2 };
  },
};
</script>

<!-- <style scoped>
.paragraph {
  color: red;
}
</style> -->
