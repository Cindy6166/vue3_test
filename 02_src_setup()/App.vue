<template>
  <h1>information</h1>
  <h2>Name: {{ name }}</h2>
  <h2>Age: {{ age }}</h2>
  <h2>Gender: {{sex}}</h2>
  <h2>a is: {{a}}</h2>
  <br>
  <button @click="sayHello">say Hello (config by vue3)</button>
  <br><br>
  <button @click="sayWelcome">say Welcome (config by vue2)</button>
  <br><br>
  <button @click="test">log the data and function from vue3 by vue2</button>
  <br><br>
  <button @click="test2">log the data and function from vue2 by setup() of vue3</button>
</template>

<script>
// import { h } from "vue";
export default {
  name: "App",
  data() {
    return {
      gender: 'Male',
      a:'vue2'
    }
  },
  methods:{
    sayWelcome(){
      alert('Welcome!')
    },
    test(){
      console.log(this.gender);
      console.log(this.name);
      console.log(this.age);
      console.log(this.sayHello);
    }
  },

  // test setup, haven't consider responsive
  setup() {
    // data
    let name = "Tom";
    let age = 18;
    let a = 'vue3' 

    //methods
    function sayHello() {
      alert(`i'm ${name}, ${age} years old!`);
    }

    function test2(){
      console.log(this.name);
      console.log(this.age);
      console.log(this.sayHello);
      console.log(this.gender);
      console.log(this.sayWelcome);
    }

    // return an object
     return{
       name,
       age,
       a,
       sayHello,
       test2
     }

    // return a function
    // return () => { return h("h1", "LALA") };
    // return () => h('h1', 'LALA')
  },
};
</script>

