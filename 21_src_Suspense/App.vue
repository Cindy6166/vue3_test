<template>
  <div class="app">
    <h3>App</h3>
    <Suspense>
      <template v-slot:default>
        <Child/>
      </template>
      <template v-slot:fallback>
        <h3>Loading...</h3>
      </template>
    </Suspense>
  </div>
</template>
<script>
// import Child from './components/Child.vue' // static import
import {defineAsyncComponent} from 'vue'
const Child = defineAsyncComponent(()=>import('./components/Child')) // async import
export default {
  name:'App',
  components:{Child},
}
</script>

<style>
.app{
  background-color: gray;
  padding: 10px;
}
</style>