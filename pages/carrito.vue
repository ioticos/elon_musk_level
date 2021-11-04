<template>
  <div style="padding: 20px">

    <h3>Productos ({{productos.length}}){{total}} {{total}} {{total}} {{total}} {{total}} {{total}}</h3>

    <!-- FORMULARIO -->
    <select @change="resetearCantidad()" v-model="productoSeleccionado">
        <option disabled  value="-1">Selecciona un Producto</option>
        <option v-for="producto, index in productos" :value="index" :key="producto.id">
            {{producto.nombre}}
        </option>
    </select>
    <input v-if="productoSeleccionado != -1" v-model.number="cantidad" min="1" :max="productos[productoSeleccionado].stock" type="number" style="width: 40px">
   
    <button @click="agregarProducto()">Agregar</button> 
    <span v-if="productoSeleccionado != -1">{{productos[productoSeleccionado].precio * cantidad}}</span> 

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
            cantidad: 1,
            llamados: 0,
            productos: [
                {
                    id: 1,
                    nombre: "Uniforme",
                    precio: 12.10,
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
                    precio: 10.70,
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
    computed: {
        total(){
            console.log("TOTAL HA SIDO LLAMADO");
            var total = 0;
            this.carrito.forEach(producto => {
              total = total + (producto.precio * producto.cantidad)
            });

            return ' $' + total;
        },
    },
    methods: {
        
        resetearCantidad(){
            this.cantidad = 1;
        },
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