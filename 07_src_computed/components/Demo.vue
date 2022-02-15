<template>
  <h1>information</h1>
  First Name: <input type="text" v-model="person.firstName">
  <br><br>
  Last Name: <input type="text" v-model="person.lastName">
  <br><br>
  <span>Full Name: {{person.fullName}}</span>
  <br>
  Full Name: <input type="text" v-model="person.fullName">
</template>

<script>
import { reactive,computed } from "vue";
export default {
  name: "Demo",
  setup() {
    // data
    let person = reactive({
      firstName: 'Tom',
      lastName: 'Cruis',
    })

    //computed -> shortcut (can't be revised)
    // person.fullName = computed(()=>{
    //   return person.firstName + '-' + person.lastName
    // })

    //computed -> common
    person.fullName = computed({
      get(){
        return person.firstName + '-' + person.lastName
      },
      set(value){
        const nameArr = value.split('-')
        person.firstName = nameArr[0]
        person.lastName = nameArr[1]
      }
    })
    
    // return an object
    return {
      person,
    };
  },
};
</script>

