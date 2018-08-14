<template>
  <div id="app">
    <ApiWatcher/>
  </div>
</template>

<script>
import ApiWatcher from "./components/ApiWatcher";

export default {
  name: "App",
  components: {
    ApiWatcher
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
