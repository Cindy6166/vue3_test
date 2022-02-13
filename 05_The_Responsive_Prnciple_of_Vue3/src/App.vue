<template>
  <h1>information</h1>
  <h2 v-show="person.name">Name: {{ person.name }}</h2>
  <h2>Age: {{ person.age }}</h2>
  <h2 v-show="person.gender">Gender: {{ person.gender }}</h2>
  <br />
  <h3>Occupation</h3>
  <h3>title: {{ person.job.title }}</h3>
  <h3>salary: {{ person.job.salary }}</h3>
  <h3>hobby: {{person.hobby}}</h3>
  <h3>test data a : {{person.job.a.b.c}}</h3>
  <button @click="changeInfo">change info</button>
  <button @click="addGender">addGender</button>
  <button @click="deleteName">deleteName</button>
</template>

<script>
import { reactive } from "vue";
export default {
  name: "App",
  setup() {
    // data
    const person = reactive({
      name: 'Tom',
      age: 18,
      job: {
        title: 'Frontend Engineer',
        salary: '80k',
        a:{
          b:{
            c:666
          }
        }
      },
      hobby: ['study', 'singing', 'dance']
    })

    //methods
    function changeInfo() {
      person.name = "LaLa",
      person.age = "20",
      person.job.title = "UI Designer",
      person.job.salary = "70k";
      person.job.a.b.c = 999,
      person.hobby[0] = 'play'
    }

    function addGender(){
      person.gender = 'Male'
    }

    function deleteName(){
      delete person.name
    }

    // return an object
    return {
      person,
      changeInfo,
      addGender,
      deleteName
    };
  },
};
</script>

