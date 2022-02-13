<template>
  <h1>information</h1>
  <h2>Name: {{ name }}</h2>
  <h2>Age: {{ age }}</h2>
  <br>
  <h3>Occupation</h3>
  <h3>title: {{ job.title }}</h3>
  <h3>salary: {{ job.salary }}</h3>
  <button @click="changeInfo">change info</button>
</template>

<script>
import {ref} from 'vue'
export default {
  name: "App",
  setup() {
    // data
    let name = ref("Tom");
    let age = ref(18);
    let job = ref({
      title: 'Frontend Engineer',
      salary:'80k'
    })

    //methods
    function sayHello() {
      alert(`i'm ${name.value}, ${age.value} years old!`);
    }

    function changeInfo() {
      name.value = 'LaLa',
      age.value = '20',
      job.value.title = 'UI Designer',
      job.value.salary = '70k'
      // console.log(job.value);
    }

    // return an object
     return{
       name,
       age,
       job,
       sayHello,
       changeInfo
     }
  },
};
</script>

