<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <Contador
    titulo="Contador1"
    v-bind:valor="calcular(1, 3)"
    :esVerdad="muestra1"
    :valor2="8"
  />
  <Contador :valor="calcular(5, 3)" :esVerdad="muestra2" />
  <button @click="cambiar(1)">Cambiar primero</button>
  <button @click="cambiar(2)">Cambiar segundo</button>
</template>

<script>
import Contador from "./components/contador.vue";
export default {
  name: "App",
  components: {
    Contador,
  },
  //no deberia programarse en el app
  methods: {
    calcular(a, b) {
      return a + b;
    },
    calcular2() {
      return "Hola Mundo";
    },
    calcular3() {
      return true;
    },
    cambiar(valor) {
      if (valor === 1) {
        this.muestra1 = !this.muestra1;
      } else {
        this.muestra2 = !this.muestra2;
      }
    },
  },
  data() {
    return {
      muestra1: true,
      muestra2: true,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
