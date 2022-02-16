<template>
  <div class="child">
    <h3>Child</h3>
    <Grandchild/>
  </div>
</template>

<script>
import {inject} from 'vue'
import Grandchild from './Grandchild'
export default {
  name:'Child',
  components:{Grandchild},
  setup(){
      let x = inject('car')
      console.log(x);
  }
}
</script>

<style>
.child{
  background-color: skyblue;
  padding: 10px;
}

</style>