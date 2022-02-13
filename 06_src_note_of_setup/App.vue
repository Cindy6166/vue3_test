<template>
  <Demo @hello="showHelloMsg" msg="Hello" school="LaLa">
    <!-- <span>Slot</span>   -->
    <template v-slot:qwe>
      <span>lala</span>
    </template>
  </Demo>>
</template>

<script>
import Demo from './components/Demo.vue'
export default {
  name:'App',
  components:{Demo},
  setup(){
    function showHelloMsg(value){
      alert(`hello, you triggered Hello event, i got param: ${value}!`)
    }

    return {
      showHelloMsg
    }
  }
}
</script>

<style>

</style>