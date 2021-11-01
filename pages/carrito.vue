<template>
  <div style="padding: 20px">

    <h3>Productos ({{productos.length}})</h3>
    <!-- FORMULARIO -->
    <select v-model="productoSeleccionado">
        <option disabled  value="-1">Selecciona un Producto</option>
        <option v-for="producto, index in productos" :value="index" :key="producto.id">
            {{producto.nombre}}
        </option>
    </select>
    <button @click="agregarProducto()">Agregar</button>
<br><br>
   Carrito:{{carrito}}

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
            ],
            carrito: []
        }
    },
    methods: {
        agregarProducto(){
            const producto = this.productos[this.productoSeleccionado];
            this.carrito.push(producto);
        }
    }
};
</script>

<style>
</style>