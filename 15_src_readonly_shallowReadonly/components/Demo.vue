<template>
  <h4>Sum is: {{sum}}</h4>
  <button @click="sum++">add</button>
  <h2>Name: {{name}}</h2>
  <h2>age: {{age}}</h2>
  <h2>Salary: {{job.j1.salary}}k</h2>
  <button @click="name+='~'">Revise Name</button>
  <button @click="age++">Increase age</button>
  <button @click="job.j1.salary++">Raise salary</button>
</template>

<script>
import { ref,reactive,toRefs,readonly,shallowReadonly } from "vue";
export default {
  name: "Demo",
  setup() {
    // data
    let sum = ref(0)
    let person = reactive({
      name: 'Tom',
      age: 20,
      job: {
        j1:{
          salary: 200
        }
      }
    })

    person = readonly(person)
    // person = shallowReadonly(sum)
    // sum = readonly(sum)
    // sum = shallowReadonly(sum)



    // return an object
    return {
      sum,
      ...toRefs(person)
    };
  },
};
</script>

