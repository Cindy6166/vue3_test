<template>
  <div class="app">
    <h3>App</h3>
  </div>
</template>

<script>
import { ref,readonly,reactive, toRefs,isRef,isReactive,isReadonly,isProxy } from 'vue'
export default {
  name:'App',
  setup(){
    let car = reactive({name: 'Rolls-Royce',price:'1500w'})
    let sum = ref(0)
    let car2 = readonly(car)

    console.log(isRef(sum));
    console.log(isReactive(car));
    console.log(isReadonly(car2));
    console.log(isProxy(car)); //isProxy: true (readonly,reactive)

    return {sum,car2,...toRefs(car)}
  }
}
</script>

<style>
.app{
  background-color: gray;
  padding: 10px;
}

</style>