<template>
  <h2>sum: {{ sum }}</h2>
  <button @click="sum++">add 1</button>
  <hr />
  <h2>mouse X: {{ point.x }}, y: {{ point.y }}</h2>
</template>

<script>
import { ref } from 'vue'
import usePoint from '../hooks/usePoint'
export default {
  name: "Demo",
  setup() {
    // data
    let sum = ref(0);
    let point = usePoint()
   
    // return an object
    return { sum, point }
  },
};
</script>

