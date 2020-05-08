<template>
  <!-- <div> -->
    <h1>Home</h1>
    <div>
      <span>count: {{ count }}</span>
      <button @click="increment()">increment</button>
    </div>
  <!-- </div> -->
</template>

<script>
import { ref } from "vue";

export default {
  name: "Home",

  setup() {
    const count = ref(0);
    function increment() {
      count.value++;
    }

    return { count, increment };
  },
};
</script>
