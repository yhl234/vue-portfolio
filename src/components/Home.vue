<template>
  <div>
    <nav>
      <Ul>
        <li>
          <a href="#">Home</a>
        </li>
        <li>
          <a href="#">Works</a>
        </li>
        <li>
          <a href="#">Resume</a>
        </li>
        <li>
          <a href="#">Contact</a>
        </li>
      </Ul>
    </nav>
    <div class="home-grid">
      <h1>Louis Lee</h1>
      <div class="social-links">
        <i class="fab fa-linkedin fa-2x"></i>
        <i class="fab fa-github-square fa-2x"></i>
        <i class="fas fa-envelope-square fa-2x"></i>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "Home"
};
</script>
<style lang="scss" scoped>
nav {
  background: transparent;
}
ul {
  display: flex;
  list-style: none;
  justify-content: flex-end;
}
li {
  padding: 1rem;
}
a {
  color: #ffffff;
}
.home-grid {
  display: grid;
}

.social-links {
  display: flex;
  justify-content: flex-start;
  i {
    margin: 0.5rem;
  }
}
</style>
