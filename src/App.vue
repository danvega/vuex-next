<template>
  <p>Count: {{ count }}</p>
  <button @click="increment()">Increment</button>
  <button @click="decrement()">Decrement</button>
</template>

<script>
import { computed } from "vue";
import { useStore } from "vuex";

export default {
  setup() {
    const store = useStore();
    const count = computed(() => store.state.count);

    function increment() {
      store.commit("increment");
    }

    function decrement() {
      store.commit("decrement");
    }

    return { count, increment, decrement };
  }
};
</script>
