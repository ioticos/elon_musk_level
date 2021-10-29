<template>
  <div>
    <variable-control titulo="Temperatura" unidad=" °C"></variable-control>
    <variable-control titulo="Humedad" unidad=" %"></variable-control>
    <variable-control titulo="Iluminación" unidad=" Lumen"></variable-control>
<variable-control titulo="Caudal" unidad=" Litros"></variable-control>

  </div>
</template>

<script>
import VariableControl from '~/components/VariableControl.vue'
  export default {
  components: { VariableControl },
    data(){
      return {
        temperatura: 10,
        humedad: 0,
        iluminacion: 0,
      }
    }
  }
</script>
