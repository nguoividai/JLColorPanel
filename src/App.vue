<template>
  <div id="app">
    <JLColorPanel />
  </div>
</template>

<script>
import JLColorPanel from "./components/JLColorPanel";

export default {
  name: "App",
  components: {
    JLColorPanel,
  },
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
  display: flex;
  justify-content: center;
}
</style>
