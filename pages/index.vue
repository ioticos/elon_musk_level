<template>
  <div>
    
    <variable-control :titulo="cuenta" unidad="°C" :max="10"></variable-control>
  
    <variable-control :titulo="cuenta * 10" unidad="%" :max="3"></variable-control>
  
  <button @click="cuenta++">SUMA 1</button>

  </div>
</template>

<script>
import VariableControl from '~/components/VariableControl.vue'
  export default {
  components: { VariableControl },
    data(){
      return {
        temperatura: 13,
        humedad: 0,
        cuenta: 0
      }
    }
  }
</script>

<style>
  .tipografia{
    font-family: Arial;
  }
  .warning{
    color:yellow
  }
  .danger{
    color: red
  }
</style>
