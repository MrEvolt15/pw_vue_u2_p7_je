<template>
  <img
    :src="imagen"
    alt="No se puede ver"
  />
  <input v-model="pregunta" type="text" placeholder="Hazme una pregunta" />
  <p>Presiona enter cuando finalices</p>

  <h1>{{ pregunta }}</h1>
  <h2>{{respuesta}}</h2>
</template>

<script>
export default {
  data() {
    return {
      pregunta: "Hola Mundo",
      respuesta: null,
      imagen: 'https://yesno.wtf/assets/yes/14-b57c6dc03aa15a4b18f53eb50d6197ee.gif',
    };
  },
  watch: {
    pregunta(value, oldValue) {
      console.log(value);
      console.log(oldValue);
      if (value.includes("?")) {
        //Programar la llamada al API para obtener el si o el no, y la imagen
        console.log("Llamar al API");
        this.fachada();
      }
    },
  },
  methods: {
    //si lleva la palabra await debe ser metodo async
    async llamarAPI() {
      
      const data = await fetch('https://yesno.wtf/api').then((resp) => resp.json());
      this.respuesta = data.answer;
      this.imagen = data.image;
      console.log(data);
    },
    //para llamar al metodo async desde otro metodo debo ponerle await
    async fachada(){
      await this.llamarAPI();
    }
  },
};
</script>

<style></style>