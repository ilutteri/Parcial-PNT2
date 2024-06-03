<template>
  <div class="container mt-3">
    <div class="jumbotron">
      <h1>Programación en Nuevas Tecnologías II</h1>
      <hr>
      <h3>Parcial - Ignacio Lutteri - Curso E</h3>
      <br>

    <Formulario />
    </div>
  </div>
</template>

<script>
import Formulario from './components/Formulario.vue'

export default {
  name: 'App',
  components: {
    Formulario
  }
}
</script>

<style>

h3{
  font-style: italic;
}

</style>
