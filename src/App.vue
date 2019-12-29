<template>
  <div id="app">
    <Home />
  </div>
</template>

<script>
import Home from "./components/Home.vue";

export default {
  name: "app",
  components: {
    Home
  }
};
</script>

<style>
* {
  box-sizing: border-box;
}
:root {
  --color-intrative: #ca3e47;
  --color-dark-one: #313131;
  --color-dark-two: #414141;
  --color-dark-three: #525252;
}
body {
  background: var(--color-dark-one);
  color: var(--color-dark-three);
  margin: 0;
  padding: 0;
}
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #abafb3;
}
</style>
