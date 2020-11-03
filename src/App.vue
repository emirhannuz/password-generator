<template>
  <div id="app" class="container rounded col-lg-4">
    <img alt="" class="mt-5 mb-5" src="./assets/image.svg" width="50%" height="60%"/>
    <PassGenerator message="Password Generator" version="v1.1" />
    <Modal></Modal>
  </div>
</template>

<script>
import PassGenerator from "./components/PassGenerator.vue";
import Modal from "./components/Modal.vue";

export default {
  name: "App",
  components: {
    PassGenerator,
    Modal,
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
  margin-top: 16px;
  background-color: white; 
  margin-bottom:10px; 
  padding-bottom:24px
}
</style>
