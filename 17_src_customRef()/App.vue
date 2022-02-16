<template>
<input type="text" v-model="keyWord">
<h3>{{keyWord}}</h3>
</template>

<script>
import {customRef} from 'vue'
export default {
  name:'App',
  setup(){
    let timer
    // custom ref
    function myRef(value,delay){
     return customRef((track, trigger)=>{
       return {
          get(){
            console.log(`read data from myRef(), data is: ${value}`);
            track() // track the changed of value
            return value
          },
          set(newValue){
            console.log(`change data from myRef(), new data is: ${newValue}`);
            clearTimeout(timer)
            timer = setTimeout(()=>{
                value = newValue
                trigger() // trigger vue to reparse tamplate
              },delay)
          }
       }
     })
    }
    //  let keyWord = ref('Hello') //ref of vue
     let keyWord = myRef('Hello', 500)

     return {keyWord}
  }
}
</script>

<style>

</style>