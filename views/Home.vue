<template>
  <h1>Home</h1>
  <div>
    <span>count: {{ count }}</span>
    <button @click="increment()">increment</button>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'Home',

  beforeRouteLeave(to, from, next) {
    console.log(this.count)
    next()
  },

  setup() {
    const count = ref(0)
    function increment() {
      count.value++
    }

    return { count, increment }
  },
}
</script>
