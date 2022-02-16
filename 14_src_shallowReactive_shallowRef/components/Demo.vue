<template>
  <h4>X.y is: {{x.y}}</h4>
  <button @click="x={y:888}">replace x</button>
  <button @click="x.y++">add</button>
  <h4>{{person}}</h4>
  <h2>Name: {{name}}</h2>
  <h2>age: {{age}}</h2>
  <h2>Salary: {{job.j1.salary}}k</h2>
  <button @click="name+='~'">Revise Name</button>
  <button @click="age++">Increase age</button>
  <button @click="job.j1.salary++">Raise salary</button>

</template>

<script>
import { reactive,toRefs, shallowReactive,shallowRef } from "vue";
export default {
  name: "Demo",
  setup() {
    // data
    // let person = shallowReactive({
    let person = reactive({
      name: 'Tom',
      age: 20,
      job: {
        j1:{
          salary: 200
        }
      }
    })

    let x = shallowRef({
      y:0
    })
    console.log(x);

    // return an object
    return {
      person,
      x,
      ...toRefs(person)
    };
  },
};
</script>

