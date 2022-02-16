<template>
  <div class="grandchild">
    <h3>Grandchild, {{car.name}} : {{car.price}}</h3>
  </div>
</template>

<script>
import {inject} from 'vue'
export default {
  name:'Grandchild',
  setup(){
      let car = inject('car')

      return {car}
  }
}
</script>

<style>
.grandchild{
  background-color: rosybrown;
  padding: 10px;
}

</style>