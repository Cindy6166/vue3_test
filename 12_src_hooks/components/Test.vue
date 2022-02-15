<template>
  <h2>test</h2>
  <h2>mouse X: {{ point.x }}, y: {{ point.y }}</h2>
</template>

<script>
import usePoint from '../hooks/usePoint'
export default {
    name:'Test',
    setup(){
        const point = usePoint()
        return {point}
    }
}
</script>

<style>

</style>