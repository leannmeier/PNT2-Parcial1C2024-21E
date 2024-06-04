<template>
  <div class="container mt-3">
    <div class="jumbotron">
      <h1>Parcial NT2 - 21E</h1>
      <h2>Alumno: Meier Leandro Agustin</h2>
      <br>
      <Textos />
      <hr>
      <Respuestas />
    </div>
  </div>
</template>

<script>
import Textos from './componentes/Textos.vue'
import Respuestas from './componentes/Respuestas.vue'

export default {
  name: 'App',
  components: {
    Textos,
    Respuestas,
  }
}
</script>

<style scoped lang="css">
  h1, h2{
    color: blue;
  }
  .jumbotron {
    padding-top: 40px;
    padding-bottom: 40px;
  }
  hr{
    background-color: #000;
  }
</style>
