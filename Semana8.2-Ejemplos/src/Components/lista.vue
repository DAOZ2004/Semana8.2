<script>
export default {
  name: "Usuarios",

  data() {
    return {
      usuarios: [
        {
          nombre: "Juan",
          apellido: "Perez",
          usuario: "jperez",
          rol: "Admin",
          estado: "activo"
        },
        {
          nombre: "Maria",
          apellido: "Lopez",
          usuario: "mlopez",
          rol: "Usuario",
          estado: "activo"
        },
        {
          nombre: "Carlos",
          apellido: "Gomez",
          usuario: "cgomez",
          rol: "Editor",
          estado: "activo"
        }
      ]
    }
  },

  computed: {
    usuariosActivos() {
      return this.usuarios.filter(u => u.estado === "activo")
    }
  },

  methods: {
    cambiarEstado(usuario) {
      usuario.estado = usuario.estado === "activo"
        ? "inactivo"
        : "activo"
    }
  }
}

</script>


<template>

    <div>
    <h2>Lista de Usuarios</h2>

    <table border="1">
      <thead>
        <tr>
          <th>Nombre</th>
          <th>Apellido</th>
          <th>Usuario</th>
          <th>Rol</th>
          <th>Estado</th>
          <th>Acción</th>
        </tr>
      </thead>

      <tbody>
        <tr v-for="usuario in usuariosActivos" :key="usuario.usuario">
          <td>{{ usuario.nombre }}</td>
          <td>{{ usuario.apellido }}</td>
          <td>{{ usuario.usuario }}</td>
          <td>{{ usuario.rol }}</td>
          <td>{{ usuario.estado }}</td>
          <td>
            <button @click="cambiarEstado(usuario)">
              Cambiar Estado
            </button>
          </td>
        </tr>
      </tbody>
    </table>

  </div>

</template>


<style scoped>

</style>