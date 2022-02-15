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
import { ref, reactive, watch } from "vue";
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

    // watch
    // case 1: watch a data in ref
    // watch(sum,(newValue,oldValue)=>{
    //   console.log(newValue, oldValue);
    // },{immediate:true})

    // case 2: watch many data in ref
    // watch([sum, msg],(newValue,oldValue)=>{
    //   console.log(newValue, oldValue);
    // },{immediate:true})

    /* case 3: watch data in reactive
       note 1: can't get correct oldValue
       note 2: open deep watch mandatorate (config deep would be invalid)
    */
    // watch(person,(newValue,oldValue)=>{
    //   console.log(newValue, oldValue)
    //,{deep:false}})

    // case 4: watch a property of data which define in reactive
    // watch(()=>person.age,(newValue,oldValue)=>{
    //   console.log(newValue, oldValue)
    // })

    // case 4: watch some property of data which define in reactive
    // watch([()=>person.age,()=>person.name],(newValue,oldValue)=>{
    //   console.log(newValue, oldValue)
    // })

    // particular case: watch deep property (object) of data which define in reactive
    watch(()=>person.job,(newValue,oldValue)=>{
      console.log(newValue, oldValue)
    }, {deep:true})

    // return an object
    return {
      sum,
      msg,
      person
    };
  },
};
</script>

