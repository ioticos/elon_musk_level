<template>

  <div style="padding: 20px">

    <!-- FORMULARIO -->
    <h3>Inscribir Alumno</h3>

    <div style="outline: 1px solid black">
      Nombre: {{ nuevoAlumno.nombre }}<br />
      Edad: {{ nuevoAlumno.edad }}<br />
      Promedio: {{ nuevoAlumno.promedio }}
    </div>
    <br />

    <label for="">Nombre:</label><br />
    <input v-model="nuevoAlumno.nombre" type="text" style="background: gray" />
    <br /><br />
    <label for="">Edad:</label><br />
    <input v-model="nuevoAlumno.edad" type="text" style="background: gray" />
    <br /><br />
    <label for="">Promedio:</label><br />
    <input
      v-model="nuevoAlumno.promedio"
      type="text"
      style="background: gray"
    />
    <button @click="alumnos.push(nuevoAlumno)">Agregar</button>

    <!-- TABLA -->
    <br />
    <h3>Alumnado:</h3>
    <table>
      <tr>
        <th>#</th>
        <th>Nombre</th>
        <th>Edad</th>
        <th>Promedio</th>
      </tr>

      <tr v-for="(alumno, index) in alumnos" :key="'alumno_' + index">
        <td>{{ index }}</td>
        <td>{{ alumno.nombre }}</td>
        <td>{{ alumno.edad }}</td>
        <td>{{ alumno.promedio }}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      nuevoAlumno: {
        nombre: "",
        edad: null,
        promedio: null,
      },
      alumnos: [],
    };
  },
};


// TABLA JS ->   edad -> AA  ; numero -> BB; nuevoAlumno -> CC; viejoAlumno -> CC

// MEMORIA RAM ->    AA   |   BB  |   CC   |   DD   |
// VALORES ->        10   |   11  |  {NEP}  

var edad = 10;
var numero = edad;
numero = 11;

var nuevoAlumno= 
      {
        nombre: "Juan",
        edad: 10,
        promedio: 11,
      }

var viejoAlumno = nuevoAlumno;


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