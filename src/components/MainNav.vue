<template>
  <div class="main-nav">
    <a class="logo" href="https://louislee.best/">
      <img src="@/assets/logo.png" width="150" height="150" />
    </a>
    <nav>
      <Ul>
        <li>
          <a href="#" data-menu="home" @click.prevent="emitMenu">Home</a>
        </li>
        <li>
          <a href="#" data-menu="about" @click.prevent="emitMenu">About</a>
        </li>
        <li>
          <a href="#" data-menu="contact" @click.prevent="emitMenu">Contact</a>
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
<style lang="less" scoped>
.main-nav {
  height: 100%;
  width: 200px;
  position: fixed;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  top: 0;
  left: 0;
  overflow-x: hidden;
  @media @mobile {
    // height: 100px;
    width: 100%;
    position: relative;
    .row();
    flex-wrap: wrap;
    a {
      display: block;
      img {
        height: 80px;
        width: 80px;
      }
    }
  }
}

nav {
  @media @mobile {
    .f-center-center();
  }
  ul {
    padding: 0;
    .col();
    list-style: none;
    justify-content: flex-end;

    @media @mobile {
      .row();
      .f-center-center();
      height: 20px;
    }
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
  min-height: 4rem;
  display: flex;
  justify-content: space-evenly;
  @media @mobile {
    min-height: 3rem;
    .f-center-center();
    // a {
    //   margin: 0 0.5rem;
    // }
  }
  a:hover {
    background: transparent;
    color: var(--color-intrative);
  }
}
</style>
