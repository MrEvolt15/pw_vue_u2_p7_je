<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <JuegoPage />
</template>

<script>
import JuegoPage from "./pages/JuegoPage.vue";

export default {
  name: "App",
  components: {
    JuegoPage,
  },
  //no deberia programarse en el app
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
  display: contents;
  justify-content: center;
}
</style>
