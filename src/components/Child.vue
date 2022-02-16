<template>
  <div class="child">
    <h3>Child</h3>
    <Grandchild/>
  </div>
</template>

<script>
import Grandchild from './Grandchild'
export default {
  name:'Child',
  components:{Grandchild},
}
</script>

<style>
.child{
  background-color: skyblue;
  padding: 10px;
}

</style>