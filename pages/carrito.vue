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
    <input v-model.number="cantidad" type="number" style="width: 40px">
    <button @click="agregarProducto()">Agregar</button>

<br><br>
  Carrito:
<pre>
{{carrito}}
</pre>
 

  </div>
</template>

<script>
export default {
    data(){
        return {
            productoSeleccionado: -1,
            cantidad: 0,
            productos: [
                {
                    id: 1,
                    nombre: "Uniforme",
                    precio: 12.40,
                    max: 5,
                    stock: 2           
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
            let producto = this.productos[this.productoSeleccionado];
            producto.cantidad = this.cantidad;
            this.carrito.push(producto);
        }
    }
};
</script>

<style>
</style>