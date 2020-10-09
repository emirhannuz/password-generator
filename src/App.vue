<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <PassGenerator message="Password Generator" version="v1.0" />
    <h1>{{ asd }}</h1>
  </div>
</template>

<script>
import PassGenerator from "./components/PassGenerator.vue";

export default {
  name: "App",
  components: {
    PassGenerator,
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
