<template>
  <h2>sum: {{sum}}</h2>
  <button @click="sum++">add 1</button>
  <hr>
  <h2>message: {{msg}}</h2>
  <button @click="msg+='!'">add !</button>
  <hr>
  <h2>Name: {{person.name}}</h2>
  <h2>age: {{person.age}}</h2>
  <h2>Salary: {{person.job.j1.salary}}k</h2>
  <button @click="person.name+='~'">Revise Name</button>
  <button @click="person.age++">Increase age</button>
  <button @click="person.job.j1.salary++">Raise salary</button>

</template>

<script>
import { ref,reactive, watchEffect } from "vue";
export default {
  name: "Demo",
  setup() {
    // data
    let sum = ref(0)
    let msg = ref('Hello!')
    let person = reactive({
      name: 'Tom',
      age: 20,
      job: {
        j1:{
          salary: 200
        }
      }
    })

    //watch
    /* watch(sum,(newValue,oldValue)=>{
      console.log(newValue,oldValue)
    },{deep:true}) */

    //watchEffect : watch what you invoke
    watchEffect(()=>{
      const x1 = sum.value
      const x2 = person.job.j1.salary
      console.log('watchEffect callback');
    })

    // return an object
    return {
      sum,
      msg,
      person
    };
  },
};
</script>

