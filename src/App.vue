<template>
  <div id="app" class="container rounded col-lg-4" style="background-color: white; padding-bottom:10px">
    <img alt="" class="mt-5 mb-5" src="./assets/image.svg" width="50%" height="60%"/>
    <PassGenerator message="Password Generator" version="v1.1" />
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

<style >
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
