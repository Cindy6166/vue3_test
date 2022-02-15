<template>
  <h4>{{person}}</h4>
  <h2>Name: {{name}}</h2>
  <h2>age: {{age}}</h2>
  <h2>Salary: {{job.j1.salary}}k</h2>
  <button @click="name+='~'">Revise Name</button>
  <button @click="age++">Increase age</button>
  <button @click="job.j1.salary++">Raise salary</button>

</template>

<script>
import { reactive,toRef, toRefs } from "vue";
export default {
  name: "Demo",
  setup() {
    // data
    let person = reactive({
      name: 'Tom',
      age: 20,
      job: {
        j1:{
          salary: 200
        }
      }
    })

    const name2 = toRef(person, 'name')
    console.log(name2); //ObjectRefImpl{}

    const x = toRefs(person)
    console.log(x);

    // return an object
    return {
      person,
      ...toRefs(person)
      // name:toRef(person,'name'),
      // age:toRef(person,'age'),
      // salary:toRef(person.job.j1,'salary')
    };
  },
};
</script>

