<template>
  <div class="home">
    <p>Hi {{ name }}, this is your number : {{ number }}</p>
  </div>
</template>

<script>
export default {
  name: "HomeView",
  setup() {
    const name = "AsZaychik";
    const number = "089519750202";

    return { name, number };
  },
};
</script>
