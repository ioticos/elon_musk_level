<template>
  <div>
    <table>
      <tr>
        <th>#</th>
        <th>Nombre</th>
        <th>Edad</th>
        <th>Promedio</th>
      </tr>

      <tr v-for="alumno, index in alumnos" :key="'alumno_' + index">
        <td>{{index}}</td>
        <td>{{alumno.nombre}}</td>
        <td>{{alumno.edad}}</td>
        <td>{{alumno.promedio}}</td>
      </tr>

    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
        alumnos: [
            {
                nombre: "Pedro",
                edad: 28,
                promedio: 8.7
            },
            {
                nombre: "Luis",
                edad: 25,
                promedio: 7.7
            },
            {
                nombre: "Ana",
                edad: 25,
                promedio: 6.7
            },
            
        ]
    }
  },
};
</script>

<style>
table {
  border-collapse: collapse;
}

table,
th,
td {
  border: 1px solid black;
}
</style>