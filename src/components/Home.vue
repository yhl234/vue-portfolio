<template>
  <div class="home">
    <!-- Photo by Patrick Tomasso on Unsplash -->
    <h1 class="test">Louis Lee</h1>
  </div>
</template>
<script>
export default {
  name: "Home"
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
  opacity: 0.1;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  position: absolute;
  z-index: -1;
}
</style>
