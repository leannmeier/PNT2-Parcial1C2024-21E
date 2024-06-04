<template>
  <div class="jumbotron">
    <form @submit.prevent>
      <input type="text" v-model="textoIngresado" placeholder="Ingrese un texto"/>
    </form>
    <div v-show="visibilidad()" >
      <p>Cantidad de caracteres: {{ cantCaracteres }}</p>
      <p>1- {{ textoCodificado }} (codificado)</p>
      <p>2- {{ textoMayuscula }} (mayuscula)</p>
      <p>3- {{ textoMinuscila }} (minuscula)</p>
      <p>4- {{ Intercambiar(true) }} (mayuscula/minuscula)</p>
      <p>5- {{ Intercambiar(false) }} (minuscula/mayuscula)</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
    textoIngresado: ''
    }
  },
  computed: {
    cantCaracteres() {
      return this.textoIngresado.length;
    },
    textoCodificado() {
      return this.textoIngresado.toLowerCase().replace(/[aeiou]/g, (char) => {
        switch (char) {
          case 'a': return 'u';
          case 'e': return 'o';
          case 'i': return 'i';
          case 'o': return 'e';
          case 'u': return 'a';
        }
      });
    },
    textoMayuscula() {
      return this.textoIngresado.toUpperCase();
    },
    textoMinuscila() {
      return this.textoIngresado.toLowerCase();
    }
  },
  methods: {
    Intercambiar(estado) {
      return this.textoIngresado.split('').map((char, index) => {
        if ((index % 2 === 0 && estado) || (index % 2 !== 0 && !estado)) {
          return char.toUpperCase();
        } 
        else {
          return char.toLowerCase();
        }
      }).join('');
    },
    visibilidad(){
      return this.textoIngresado.length
    }
  }
}
</script>

<style scoped lang="css">
  .jumbotron{
    font-weight: bold;
  }
</style>
