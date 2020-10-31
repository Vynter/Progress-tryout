<template>
  <div id="app">
    <div class="container">
      <p>s</p>

      <img alt="Vue logo" src="./assets/logo.png" />
      <progressbar class="mt-5"></progressbar>
    </div>
  </div>
</template>

<script>
import progressbar from "./components/Progressbar.vue";

export default {
  name: "App",
  components: {
    progressbar,
  },
};
</script>

<style>
#app {
  text-align: center;
  /*font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;*/
}
</style>
