<template>
  <div style="padding: 20px">
    <!-- FORMULARIO -->
    <select v-model="productoSeleccionado">
        <option disabled  value="-1">Selecciona un Producto</option>
        <option v-for="producto in productos" :value="producto.id" :key="producto.id">
            {{producto.nombre}}
        </option>
    </select>

    {{productoSeleccionado}}
  </div>
</template>

<script>
export default {
    data(){
        return {
            productoSeleccionado: -1,
            productos: [
                {
                    id: 1,
                    nombre: "Uniforme",
                    precio: 12.40,
                    max: 5,
                    stock: 10           
                },
                {
                    id: 2,
                    nombre: "Libro A",
                    precio: 12.40,
                    max: 2,
                    stock: 10           
                },
                {
                    id: 3,
                    nombre: "Mapa",
                    precio: 10.40,
                    max: 100,
                    stock: 5           
                },
                {
                    id: 4,
                    nombre: "Diccionario",
                    precio: 9.40,
                    max: 2,
                    stock: 100           
                },
            ]
        }
    }
};
</script>

<style>
</style>