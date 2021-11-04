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
    <button @click="agregarNuevoAlumno()">Agregar</button>

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
  mounted() {
    this.alumnos = JSON.parse(window.localStorage.getItem("alumnado"));
  },
  methods: {
    agregarNuevoAlumno() {
      const { ...nuevoAlumnoCopy } = this.nuevoAlumno;
      this.alumnos.push(nuevoAlumnoCopy);

      window.localStorage.setItem("alumnado", JSON.stringify(this.alumnos));
    },
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