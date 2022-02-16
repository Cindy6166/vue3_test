<template>
  <div class="app">
    <h3>App, {{name}} : {{price}}</h3>
    <Child/>
  </div>
</template>

<script>
import { reactive, toRefs, provide } from 'vue'
import Child from './components/Child.vue'
export default {
  name:'App',
  components:{Child},
  setup(){
    let car = reactive({name: 'Rolls-Royce',price:'1500w'})

    provide('car', car) // provide data to child and grandchild

    return {...toRefs(car)}
  }
}
</script>

<style>
.app{
  background-color: gray;
  padding: 10px;
}

</style>