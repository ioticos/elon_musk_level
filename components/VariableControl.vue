<template>
  <div>
    <h4>Control de {{titulo}}</h4>
    <button @click="valor--">Disminuir</button>
    <span>{{ valor }}</span><span> {{unidad}}</span>
    <button :disabled="valor >= max"  @click="valor++">Aumentar</button>
    <br /><br />
  </div>
</template>

<script>
export default {
    props:{
      max:{},
      titulo: {
        type: String,
        required: true,
        description: "Aqui se pasará el título que el componente mostrará." 
      },
      unidad: {
        type: String
      }
    },
    data(){
        return{
            valor: 0
        }
    }
};
</script>

<style>

</style>





