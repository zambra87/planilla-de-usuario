<template>
  <div class="form-wrapper mt-4 mx-5">
    <form>
      <div class="mb-3">
        <label class="form-label">Nombre</label>
        <input class="form-control" v-model="usuario.nombre" />
      </div>
      <div class="mb-3">
        <label class="form-label">Nacionalidad</label>
        <select class="form-select" v-model="usuario.nacionalidad">
          <option value="chile">Chile</option>
          <option value="extranjero">Extranjero</option>
        </select>
      </div>
      <div class="mb-3">
        <label class="form-label">Género</label>
        <div class="d-flex gap-3">
          <div class="form-check">
            <input class="form-check-input" type="radio" name="flexRadioDefault" id="m" value="m"
              v-model="usuario.genero" />
            <label class="form-check-label fw-normal" for="m">Masculino</label>
          </div>
          <div class="form-check">
            <input class="form-check-input" type="radio" name="flexRadioDefault" id="f" value="f"
              v-model="usuario.genero" />
            <label class="form-check-label fw-normal" for="f">Femenino</label>
          </div>
        </div>
      </div>
 
      <div class="mb-3">
        <label class="form-label">Dirección de Residencia</label>
        <input class="form-control" v-model="usuario.direccion" placeholder="Somewhere in Indiana, USA" />
      </div>
 
      <div class="mb-3">
        <label class="form-label">Continentes Visitados</label>
        <div class="d-flex flex-wrap gap-3">
          <div class="form-check" v-for="continente in continentes" :key="continente">
            <input
              class="form-check-input"
              type="checkbox"
              :id="continente"
              :value="continente"
              v-model="usuario.continentesVisitados"
            />
            <label class="form-check-label" :for="continente">{{ continente }}</label>
          </div>
        </div>
      </div>
    </form>
  </div>
 
  <div class="planilla text-center mt-5 w-75 mx-auto">
    <h1>Planilla de Usuario</h1>
    <hr />
    <table class="table table-striped">
      <thead>
        <tr>
          <th>Nombre</th>
          <th>Nacionalidad</th>
          <th>Género</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>{{ usuario.nombre }}</td>
          <td>{{ usuario.nacionalidad }}</td>
          <td>{{ usuario.genero }}</td>
        </tr>
        <tr>
          <th colspan="4">Dirección</th>
        </tr>
        <tr>
          <td colspan="4">{{ usuario.direccion }}</td>
        </tr>
        <tr>
          <th colspan="4">Continentes Visitados</th>
        </tr>
        <tr>
          <td colspan="4">{{ usuario.continentesVisitados.join(', ') }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>
 
<script>
export default {
  name: "App",
  data() {
    return {
      usuario: {
        nombre: "",
        nacionalidad: "",
        genero: "",
        direccion: "",
        continentesVisitados: [], 
      },
      continentes: ["Asia", "Europa", "África", "América", "Oceanía"], 
    };
  },
};
</script>
 
<style scoped>
.form-wrapper {
  display: block;
  margin: 40px;
  padding: 60px;
  border: 1px solid #ccc;
  border-radius: 15px;
  background-color: #f9f9f9;
}
 
.planilla {
  margin-top: 50px;
  width: 80%;
  margin-left: auto;
  margin-right: auto;
}
</style>
 