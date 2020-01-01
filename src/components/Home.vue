<template>
  <div class="home">
    <!-- Photo by Patrick Tomasso on Unsplash -->
    <div class="center-center">
      <h1>Louis Lee</h1>
    </div>
    <Works />
  </div>
</template>
<script>
import Works from "./Works";
export default {
  name: "Home",
  components: {
    Works
  }
};
</script>
<style lang="scss" scoped>
h1 {
  font-family: "Fredericka the Great", cursive;
}
.home {
  display: grid;
  position: relative;
}
.home::after {
  content: "";
  background-image: url("../assets/img/bg.jpg");
  // Photo by Patrick Tomasso on Unsplash
  background-size: cover;
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
</style>
