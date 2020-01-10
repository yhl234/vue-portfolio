<template>
  <div id="app">
    <MainNav v-on:menuClicked="changeMenu" />
    <Home :menu="this.menu" />
  </div>
</template>

<script>
import Home from "./components/Home.vue";
import MainNav from "./components/MainNav.vue";
export default {
  name: "app",
  components: {
    Home,
    MainNav
  },
  data: function() {
    return {
      menu: "home"
    };
  },
  methods: {
    changeMenu(selected) {
      this.menu = selected;
    }
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
  --color-text: #abafb3;
}
body {
  background: var(--color-dark-one);
  color: var(--color-dark-three);
  margin: 0;
  padding: 0;
}
#app {
  font-family: "Cabin Sketch", cursive;
  text-align: center;
  color: var(--color-text);
  display: grid;
  grid-template-areas: "nav page";
  grid-template-columns: 200px auto;
  min-height: 100vh;
}
.home {
  grid-area: page;
}
.main-nav {
  grid-area: nav;
}

a,
button {
  color: #ffffff;
  transition: all 200ms ease-in-out;
}
a:hover,
button:hover {
  background: var(--color-intrative);
}
.center-center {
  display: grid;
  justify-content: center;
  align-items: center;
}
[v-cloak] {
  display: none;
}
</style>
