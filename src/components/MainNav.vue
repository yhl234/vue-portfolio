<template>
  <div class="main-nav">
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
    <div class="social-links">
      <a href="#">
        <i class="fab fa-linkedin fa-2x"></i>
      </a>
      <a href="#">
        <i class="fab fa-github-square fa-2x"></i>
      </a>
      <a href="#">
        <i class="fas fa-envelope-square fa-2x"></i>
      </a>
    </div>
  </div>
</template>
<script>
export default {
  name: "MainNav"
};
</script>
<style lang="scss" scoped>
.main-nav {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}
nav {
  ul {
    padding: 0;
    display: flex;
    flex-direction: column;
    list-style: none;
    justify-content: flex-end;
    li {
      padding: 1rem;
      a {
        display: block;
        padding: 0.3rem;
      }
    }
  }
}
.social-links {
  display: flex;
  justify-content: space-evenly;
  overflow: hidden;

  a:hover {
    background: transparent;
    color: var(--color-intrative);
  }
}
</style>
