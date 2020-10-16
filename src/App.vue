<template>
  <div id="app">
    <HeaderTop></HeaderTop>
    <Contenu></Contenu>
  </div>
</template>

<script>
import Contenu from "./components/Contenu.vue";
import HeaderTop from "./components/HeaderTop.vue";

export default {
  name: "App",
  components: {
    Contenu,
    HeaderTop,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 80px;
}
</style>
