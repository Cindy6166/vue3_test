<template>
  <h1>information</h1>
  <h2>Name: {{ person.name }}</h2>
  <h2>Age: {{ person.age }}</h2>
  <button @click="test">Trigger Hello event of Demo
  </button>
</template>

<script>
import { reactive } from "vue";
export default {
  name: "Demo",
  props:['msg','school'],
  emits:['hello'],
//   beforeCreate(){
//       console.log('---beforeCreate---');
//   },
  setup(props,context) {
    //   console.log('---setup---',props,context);
    //   console.log('---setup---',context.attrs); //like $attrs in Vue2
    //   console.log('---setup---',context.emit); //trigger customized event
      console.log('---setup---',context.slots); //slots

    // data
    const person = reactive({
      name: 'Tom',
      age: 18,
    })

    //methods
    function test(){
       context.emit('hello', 666) 
    }
    
    // return an object
    return {
      person,
      test
    };
  },
};
</script>

