<template>
  <div class="home">
    <!-- Photo by Patrick Tomasso on Unsplash -->
    <div class="top">
      <h1>Louis Lee</h1>
      <span>I develop optimized modern web app</span>
    </div>
    <template v-if="this.menu === 'home'">
      <Works />
    </template>
    <template v-if="this.menu === 'contact'">
      <Contact />
    </template>
    <template v-if="this.menu === 'about'">
      <About />
    </template>
  </div>
</template>
<script>
import Works from "./Works";
import Contact from "./Contact";
import About from "./About";
export default {
  name: "Home",
  props: ["menu"],
  components: {
    Works,
    Contact,
    About
  }
};
</script>
<style lang="less" scoped>
.home {
  display: grid;
  position: relative;
  grid-template-areas: "top" "bottom";
  grid-template-rows: 200px auto;
  width: 100%;
  &::after {
    content: "";
    background-image: url("../assets/img/bg.jpg");
    // Photo by Patrick Tomasso on Unsplash
    background-size: cover;
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
    opacity: 0.1;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    position: absolute;
    z-index: -1;
  }
  .top {
    font-family: "Fredericka the Great", cursive;

    grid-area: top;
    display: grid;
    grid-template-rows: 140px 50px;
    justify-content: center;
    align-items: center;
    h1 {
      align-self: end;
      margin: 0;
    }
  }
  .bottom {
    grid-area: bottom;
    padding: 0 3rem;
    transition: all 5000s ease-in-out;
  }
}
</style>
