<template>
  <div class="bottom" v-cloak>
    <h2>Achievements</h2>
    <ul>
      <li>2020, Graduated from Georgian College Interactive Media Design-Web program</li>
      <li>2019, Dean's List of Fall semester</li>
      <li>
        2019, Web developer co-op in
        <a href="https://www.vacationpal.ca/">VacationPal</a>
      </li>
      <li>2019, Dean's List of winter semester</li>
      <li>2019, Dean's List of Fall semester</li>
      <li>2018, Rookie-of-the-Year in U-Trust Real Estate, Taipei, Taiwan</li>
      <li>2016, Volunteer, Culture to Communication program, Corner Brook, NL</li>
      <li>2016, Exchange student, Memorial University of Newfoundland, Corner Brook, NL</li>
      <li>2016, Bachelor of Education, National Chi Nan University, Puli, Taiwan</li>
    </ul>
    <h2>Pet Projects</h2>
    <ul>
      <li>
        <a href="https://github.com/yhl234/react-interface">Learning React.js</a>
      </li>
      <li>
        <a href="https://github.com/yhl234/play-node-js-crawler">Telegram crawler bot</a>
      </li>
    </ul>
    <h2>Next Step</h2>
    <ul>
      <li>Less Css</li>
      <li>Arduino</li>
    </ul>
  </div>
</template>
<script>
export default {
  name: "about"
};
</script>
<style scoped lang="less">
.home {
  .bottom {
    margin: 0 auto;
    @media @mobile {
      padding: 0 1rem;
    }
  }
}
ul {
  // margin: 0 10rem;
  list-style-position: inside;
}
li {
  text-align: left;
  margin-bottom: 0.5rem;
}
h2 {
  text-align: left;
}
</style>