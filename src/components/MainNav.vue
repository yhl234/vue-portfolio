<template>
  <div class="main-nav">
    <a href="https://louislee.best/">
      <img src="@/assets/logo.png" width="150" height="150" />
    </a>
    <nav>
      <Ul>
        <li>
          <a href="#" data-menu="home" @click="emitMenu">Home</a>
        </li>
        <li>
          <a href="#" data-menu="about" @click="emitMenu">About</a>
        </li>
        <li>
          <a href="#" data-menu="contact" @click="emitMenu">Contact</a>
        </li>
      </Ul>
    </nav>
    <div class="social-links">
      <a href="https://www.linkedin.com/in/louis-lee-a85159129" title="Louis Lee">
        <i class="fab fa-linkedin fa-2x"></i>
      </a>
      <a href="https://github.com/yhl234" title="yhl234">
        <i class="fab fa-github-square fa-2x"></i>
      </a>
      <a href="mailto:leejepn@gmail.com" title="leejepn@gmail.com">
        <i class="fas fa-envelope-square fa-2x"></i>
      </a>
    </div>
  </div>
</template>
<script>
export default {
  name: "MainNav",
  methods: {
    emitMenu(e) {
      this.$emit("menuClicked", e.target.dataset.menu);
    }
  }
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
      padding: 1rem 0;
      a {
        display: block;
        padding: 0.5rem;
        text-decoration: none;
      }
    }
  }
}
.social-links {
  display: flex;
  justify-content: space-evenly;
  a:hover {
    background: transparent;
    color: var(--color-intrative);
  }
}
</style>
