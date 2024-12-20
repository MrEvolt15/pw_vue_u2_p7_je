<template>
  <h2>{{ titulo }}:{{valor2}}</h2>
  <p>{{ valor }} <sup>2</sup>= {{ calcularCuadradoComputed }}</p>
  <p>{{ numero }} <sup>2</sup>= {{ calcularCuadradoComputed }}</p>
  <div>
    <button v-on:click="incrementar()">+1</button>
    <button @click="decrementar()">-1</button>
  </div>
  <div v-if="esVerdad">
    <h1>FELIZ NAVIDAD!!!</h1>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero: this.valor,
      
    };
  },
  methods: {
    calcularCuadrado() {
        console.log("Método calcularCuadrado");
      return this.numero * this.numero;
    },
    incrementar() {
      this.numero++;
    },
    decrementar() {
      this.numero--;
    },
  },
  computed:{
    calcularCuadradoComputed(){
        console.log("Método calcularCuadradoComputed");
        return this.numero * this.numero;
    }
  },
  //primera forma de declaracion de un props
  //props:["titulo","valor"]
  //segunda forma de declaracion de un props
  props:{
    titulo:{
      type: String,
      required: false,
      default: "Titulo",
      validator(value){
        return value.includes('a');
      }
    },

    valor: Number,
    valor2:{
      type: Number,
      required: false,
      default: 78,
      validator(value){
        //programo mi validacion bajo mi ciriterio y retorno true cuando es valido para mi y false cuando no
        return value <= 77;
      }
    },
    esVerdad:{
      type: Boolean,
      required: true
    },
    arreglo: Array,
    fecha: Date,
    objeto: Object,
  }
};
</script>

<style>
h2 {
  color: #8a93de;
  box-shadow: 0px 0px 10px 0px #8a93de;
}
p {
  color: #8a93de;
  font-size: 20px;
}
button {
  background-color: #000f98;
  padding: 10px 20px;
  font-size: 16px;
  border-radius: 10px;
  gap: 10px;
  border: 1px solid #ffffff;
  color: white;
  cursor: pointer;
  margin: 0px 5px;
}
button:hover {
  background-color: #0000ff;
}

</style>