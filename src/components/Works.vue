<template>
  <div
    class="works bottom"
    :class="{grabbing:isDown}"
    ref="cards"
    @mousedown.prevent="mousedown"
    @mouseup="mouseup"
    @mouseleave="mouseleave"
    @mousemove="mousemove"
    v-cloak
  >
    <div class="card" v-for="(i, index) in works" :key="index">
      <div class="imgContainer">
        <img :src="i.img" loading="lazy" />
      </div>
      <div>
        <span>
          <a>{{ i.name }}</a> |
          <a>{{ i.category }}</a>
        </span>
      </div>
      <p>{{ i.description }}</p>
      <div class="card-btns">
        <a :href="i.code" class="code">Code</a>
        <a :href="i.url" class="live">Live</a>
      </div>
    </div>
  </div>
</template>
<script>
const works = [
  {
    img: "/images/projects/ES6-Twitter-Clone.png",
    name: "ES6 Twitter Clone<",
    category: "JavaScript",
    description:
      "Twitter clone made by ES6 Javascript, Giphy api, emoji api and Mockaroo.",
    code: "https://github.com/yhl234/ES6-Twitter-Clone",
    url: "https://19f-adv-client-side-javascript.yhl234.now.sh/"
  },
  {
    img: "/images/projects/vue-cli-trivia.png",
    name: "Vue.js Trivia",
    category: "Vue.Js",
    description:
      "Vue.js based trivia game using Trivia API, chart.js and chart.js",
    code: "https://github.com/yhl234/vue-cli-trivia",
    url: "https://vue-cli-trivia.now.sh/"
  },
  {
    img: "/images/projects/layout-with-flexbox-and-grid.png",
    name: "Responsive Layout",
    category: "CSS",
    description: "Recreate a Bootstrap template without using Bootstrap",
    code: "https://github.com/yhl234/layout-with-flexbox-and-grid",
    url: "https://layout-with-flexbox-and-grid.now.sh/"
  },
  {
    img: "/images/projects/refactoring-an-Infographic.png",
    name: "Responsive Layout",
    category: "CSS",
    description:
      "Convert a brochure in PDF into a fully responsive Web page or interface using only text and vector-based",
    code: "https://github.com/yhl234/Refactoring-an-Infographic",
    url: "https://refactoring-an-infographic.now.sh/"
  },
  {
    img: "/images/projects/lazy-tulip-ui-redesign.png",
    name: "Lazy Tulip UI Redesign",
    category: "Teamwork",
    description:
      "A modern redesign of a local cafe's website using HTML, CSS and JavaScript",
    code: "https://github.com/aryafilsoofi/Lazy-Tulip-UI-Redesign",
    url: "https://lazy-tulip-ui-redesign.now.sh/"
  },
  {
    img: "/images/projects/express-portfolio.png",
    name: "Express Portfolio",
    category: "Express.js",
    description: "A Express portfolio made by express, hbs, less and Heroku",
    code: "https://github.com/yhl234/express-portfolio",
    url: "https://yhl234-express-portfolio.herokuapp.com/"
  },
  {
    img: "/images/projects/.png",
    name: "ONNI",
    category: "Teamwork & ASP.NET core 2.2",
    description:
      "A KickStarter-like Social innovation platform for a client from Georgian ",
    code: "https://github.com/Ryan-Gee/onni",
    url: "http://onnidev.azurewebsites.net/"
  },
  {
    img: "/images/projects/.png",
    name: "Mountain Shop",
    category: "WordPress",
    description:
      "Fully custom WordPress e-commerce site using Underscore, WooCommerce, and custom post type.",
    code: "https://github.com/yhl234/mountain-shop-wordpress-theme",
    url: "https://yhl234.xyz/"
  }
];
export default {
  name: "Works",
  data: function() {
    return {
      works,
      isDown: false,
      start: 0
    };
  },
  methods: {
    mousedown(e) {
      this.isDown = true;
      this.start = e.pageX;
    },
    mouseup() {
      this.isDown = false;
    },
    mouseleave() {
      this.isDown = false;
    },
    mousemove(e) {
      if (this.isDown === false) {
        return;
      }
      const walk = this.start - e.pageX;
      const cards = this.$refs.cards;
      cards.scrollLeft += walk;
      console.log(cards.scrollLeft);
    }
  }
};
</script>
<style lang="scss" scoped>
.works {
  overflow-x: scroll;
  width: 100%;
  display: flex;
  cursor: grab;
}
.grabbing {
  cursor: grabbing;
}
.card {
  overflow: hidden;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  border: 1px solid rgba(255, 255, 255, 0.664);
  margin: 2rem;
  min-width: 300px;
  max-width: 300px;
  height: 400px;
  p {
    margin-top: 0;
  }
  .card-btns {
    display: flex;
    a {
      flex: 1 0;
      padding: 0.5rem;
      border: 0.5px solid #fff;
      border-collapse: collapse;
    }
  }
}
.imgContainer {
  width: 300px;
  height: 200px;
  overflow: hidden;
  img {
    transition: all 3s ease-in-out;
    height: 200px;
    width: auto;
    &:hover {
      scale: 1.2;
    }
  }
}
</style>
