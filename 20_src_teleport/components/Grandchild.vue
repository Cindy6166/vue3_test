<template>
  <div class="grandchild">
    <h3>Grandchild</h3>
    <Dialog/>
  </div>
</template>

<script>
import Dialog from './Dialog.vue'
export default {
  name:'Grandchild',
  components:{Dialog}
}
</script>

<style>
.grandchild{
  background-color: rosybrown;
  padding: 10px;
}

</style>