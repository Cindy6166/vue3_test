<template>
  <h4>Sum is: {{sum}}</h4>
  <button @click="sum++">add</button>
  <h2>Name: {{name}}</h2>
  <h2>age: {{age}}</h2>
  <h2>Salary: {{job.j1.salary}}k</h2>
  <h3 v-show="person.car">car:{{person.car}}</h3>
  <button @click="name+='~'">Revise Name</button>
  <button @click="age++">Increase age</button>
  <button @click="job.j1.salary++">Raise salary</button>
  <button @click="showRawPerson">raw person</button>
  <button @click="addCar"> add car</button>
  <button @click="person.car.name +='!'">replace car</button>
  <button @click="person.car.price++">replace price</button>
  <button @click="changePrice">change price</button>
</template>

<script>
import { ref,reactive,toRefs, toRaw, markRaw} from "vue";
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
      },
    })

    function showRawPerson(){
      const p = toRaw(person)
      p.age++
      console.log(p);
    }

    function addCar(){
      let car = {name:'BMW',price:400}
      person.car = markRaw(car)
    }

    function changePrice(){
      person.car.price++
      console.log(person.car.price);
    }

    // return an object
    return {
      showRawPerson,
      addCar,
      changePrice,
      person,
      sum,
      ...toRefs(person)
    };
  },
};
</script>

