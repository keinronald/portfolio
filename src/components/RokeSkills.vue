<template>
  <section class="container">
    <h2>Skills</h2>
    <div class="skills">
      <div
        v-for="skill in skills"
        :key="skill.id"
        :style="`background-color: ${skill.color}`"
        class="icon">
        <img
          alt="Vue"
          class="icon__image"
          height="100"
          src="./../assets/images/skills/vue.png"
          width="100"
        />
        <p class="icon__description">{{ skill.title }}</p>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: "RokeSkills",
  data() {
    return {
      skills: [
        {
          title: "HTML 5",
          id: "html",
          color: "#f3d8c1",
          rating: 1,
        },
        {
          title: "CSS 3",
          id: "css",
          color: "#c1dff3",
          rating: 1,
        },
        {
          title: "SCSS",
          id: "scss",
          color: "#eac1f3",
          rating: 1,
        },
        {
          title: "Vue.js",
          id: "vue",
          color: "#c1f3de",
          rating: 1,
        },
        {
          title: "Angular",
          id: "angular",
          color: "#f3c1c1",
          rating: 1,
        },
        {
          title: "Laravel",
          id: "laravel",
          color: "#f3c1c1",
          rating: 1,
        },
        {
          title: "git",
          id: "ps",
          color: "#bebebe",
          rating: 1,
        },
        {
          title: "Photoshop",
          id: "ps",
          color: "#c1dff3",
          rating: 1,
        },
        {
          title: "Figma",
          id: "figma",
          color: "#bebebe",
          rating: 1,
        },
      ],
    };
  }
};
</script>

<style lang="scss" scoped>
.skills {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}

.icon {
  height: 200px;
  width: 200px;
  background-color: #c1f3de;
  border-radius: 200px;
  margin: 25px;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  transition: background-color 250ms ease-in-out;

  // drop-shadow
  &::after {
    content: "";
    position: absolute;
    height: 200px;
    width: 200px;
    border-radius: 200px;

    z-index: -1;
    box-shadow: 0 5px 15px rgba(180, 135, 200, 0.3);
    opacity: 0;
    -webkit-transition: all 250ms ease-in-out;
    transition: all 250ms ease-in-out;
  }

  &:hover {
    opacity: 0.5;

    &::after {
      opacity: 1;
    }
  }

  &__image {
  }

  &__description {
    margin-bottom: 0;
    font-weight: bold;
  }
}
</style>
