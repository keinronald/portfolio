<template>
  <section class="container container--no-padding">
    <h2>Skills</h2>
    <div class="skills">
      <roke-circular-icon
        v-for="skill in skills"
        :key="skill.id"
        :title="skill.title"
        :color="skill.color"
        :logo="skill.logo"
      />
    </div>
  </section>
</template>

<script>
import RokeCircularIcon from "@/components/shared/RokeCircularIcon";
export default {
  name: "RokeSkills",
  components: { RokeCircularIcon },
  data() {
    return {
      vueLogo: 'https://vuejs.org/images/logo.png',
      skills: [
        {
          title: "HTML 5",
          id: "html",
          logo: require("../assets/images/skills/html.png"),
          color: "#f3d8c1",
          rating: 1,
        },
        {
          title: "CSS 3",
          id: "css",
          logo: require("../assets/images/skills/css.png"),
          color: "#c1dff3",
          rating: 1,
        },
        {
          title: "SCSS",
          id: "scss",
          logo: require("../assets/images/skills/scss.png"),
          color: "#eac1f3",
          rating: 1,
        },
        {
          title: "Vue.js",
          id: "vue",
          logo: require("../assets/images/skills/vue.png"),
          color: "#c1f3de",
          rating: 1,
        },
        {
          title: "Angular",
          id: "angular",
          logo: require("../assets/images/skills/angular.png"),
          color: "#f3c1c1",
          rating: 1,
        },
        {
          title: "Laravel",
          id: "laravel",
          logo: require("../assets/images/skills/laravel.png"),
          color: "#f3c1c1",
          rating: 1,
        },
        {
          title: "git",
          id: "git",
          logo: require("../assets/images/skills/git.png"),
          color: "#bebebe",
          rating: 1,
        },
        {
          title: "Photoshop",
          logo: require("../assets/images/skills/photoshop.png"),
          id: "photoshop",
          color: "#c1dff3",
          rating: 1,
        },
        {
          title: "Figma",
          id: "figma",
          logo: require("../assets/images/skills/figma.png"),
          color: "#bebebe",
          rating: 1,
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.skills {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
</style>
