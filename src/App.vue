<template>
  <div id="app">
    <Tab/>
    <div class="body">
      <router-view/>
    </div>
  </div>
</template>

<script>
import Tab from "@/components/Tab";
import "@/assets/style.scss";

export default {
  name: "App",
  components: { Tab }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  background-color: lightgray;
  height: 100%;
  position: absolute;
  width: 100%;
  margin: 0;
  left: 0;
  .body {
    margin: 0;
    margin-top: 100px;
  }
}
</style>
