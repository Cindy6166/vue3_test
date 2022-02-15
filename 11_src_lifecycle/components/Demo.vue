<template>
  <h2>sum: {{sum}}</h2>
  <button @click="sum++">add 1</button>
</template>

<script>
import { onBeforeUnmount,onBeforeMount, onBeforeUpdate, onMounted, onUnmounted, onUpdated, ref } from "vue";
export default {
  name: "Demo",
  setup() {
    // data
    let sum = ref(0)

    console.log('setup');

    // lifecycle by Composition API
    onBeforeMount(()=>{
      console.log('onBeforeMount');
    }),
    onMounted(()=>{
      console.log('onMounted');
    }),
    onBeforeUpdate(()=>{
      console.log('onBeforeUpdate');
    }),
    onUpdated(()=>{
      console.log('onUpdated');
    }),
    onBeforeUnmount(()=>{
      console.log('onBeforeUnmount');
    }),
    onUnmounted(()=>{
      console.log('onUnmounted');
    })


    // return an object
    return { sum };
  },
  //optional config
  //#region
  // beforeCreate(){
  //   console.log('beforeCreate');
  // },
  // created(){
  //   console.log('created');
  // },
  // beforeMount(){
  //   console.log('beforeMount');
  // },
  // mounted(){
  //   console.log('mounted');
  // },
  // beforeUpdate(){
  //   console.log('beforeUpdate');
  // },
  // updated(){
  //   console.log('updated');
  // },
  // beforeUnmount(){
  //   console.log('beforeUnmount');
  // },
  // unmounted(){
  //   console.log('unmounted');
  // }
  //#endregion
};
</script>

