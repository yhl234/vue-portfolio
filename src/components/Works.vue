<template>
  <div class="works bottom" :class="{grabbing:isDown}" ref="cards" v-cloak>
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
    img: "/images/projects/pause-collection.png",
    name: "Pause Collection",
    category: "WordPress",
    description: "Pause Collection is a custom WordPress WooCommercer theme",
    code: "https://github.com/yhl234/Pause-Collection",
    url: "https://yhl234.xyz/"
  },
  {
    img: "/images/projects/onni.png",
    name: "ONNI",
    category: "Teamwork & ASP.NET core 2.1",
    description:
      "A KickStarter-like Social innovation platform for a client from Georgian ",
    code: "https://github.com/Ryan-Gee/onni",
    url: "http://onnidev.azurewebsites.net/"
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
    img: "/images/projects/ES6-Twitter-Clone.png",
    name: "ES6 Twitter Clone",
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
    img: "/images/projects/express-portfolio.png",
    name: "Express Portfolio",
    category: "Express.js",
    description: "A Express portfolio made by express, hbs, less and Heroku",
    code: "https://github.com/yhl234/express-portfolio",
    url: "https://yhl234-express-portfolio.herokuapp.com/"
  },

  {
    img: "/images/projects/checkout-form.png",
    name: "Checkout Form",
    category: "CSS",
    description: "A simple animated checkout from",
    code: "https://github.com/yhl234/checkout-form-animation",
    url: "https://checkout-form-animation.now.sh/"
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
  methods: {}
};
</script>
<style lang="less" scoped>
.works {
  // overflow-x: scroll;
  flex-wrap: wrap;
  width: 100%;
  display: flex;
  justify-content: center;
  // cursor: grab;
}
// .grabbing {
//   cursor: grabbing;
// }
.card {
  overflow: hidden;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  border: 1px solid rgba(255, 255, 255, 0.664);
  border-radius: 0.5rem;
  margin: 1.3rem;
  min-width: 250px;
  max-width: 280px;
  height: 400px;
  p {
    margin-top: 0;
  }
  .card-btns {
    display: flex;
    border-radius: 0 0 0.5rem 0.5rem;
    a {
      flex: 1 0;
      padding: 0.5rem;
      border: 0.2px solid #fff;
      border-collapse: collapse;
    }
  }
}
.imgContainer {
  width: 100%;
  height: 210px;
  overflow: hidden;
  img {
    transition: all 3s ease-in-out;
    height: 210px;
    width: auto;
    &:hover {
      scale: 1.2;
    }
  }
}
</style>
