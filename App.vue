<template>
  <h1>Hello Vite + Vue 3!</h1>
  <p>Edit ./App.vue to test hot module replacement (HMR).</p>
  <p>
    <span>Count is: {{ count }}</span>
    <button @click="count++">increment</button>
  </p>
  <div>
    <hr />
    <button @click="toggle">toggle</button>
    <hr />
    <Home></Home>
    <hr />
    <RouterView />
  </div>
</template>

<script>
import { ref, shallowRef, h } from 'vue'
import Home from './views/Home.vue'
import About from './views/About.vue'

const Component = shallowRef(Home)

const RouterView = {
  setup(props, { attrs }) {
    return () => {
      console.log('attrs:', Object.keys(attrs))
      return h(Component.value)
    }
  },
}

export default {
  setup() {
    let count = ref(0)
    function toggle() {
      Component.value = Component.value === Home ? About : Home
    }

    return { count, toggle }
  },

  components: { RouterView, Home },
}
</script>

<style scoped>
h1 {
  color: #4fc08d;
}

h1,
p {
  font-family: Arial, Helvetica, sans-serif;
}
</style>
