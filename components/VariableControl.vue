<template>
  <div>
    <h4>Control de {{titulo}}</h4>
    <button @click="valor--">Disminuir</button>
    <span>{{ valor }}</span><span> {{unidad}}</span>
    <button @click="valor++">Aumentar</button>
    <br /><br />
  </div>
</template>

<script>
export default {
    props:["titulo","unidad"],
    data(){
        return{
            valor: 0
        }
    }
};
</script>

<style>
</style>