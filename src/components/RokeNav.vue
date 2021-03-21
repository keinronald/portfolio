<template>
  <nav class="nav" :class="{ 'nav--scrolled': !onTop }">
    <div class="container container--no-padding nav__container">
      <router-link to="/">
        <img
          class="nav__logo"
          :src="require('../assets/images/logo.png')"
          height="50"
          alt="Logo"
        />
      </router-link>
      <router-link class="nav__link" to="/">Home</router-link>
      <a class="nav__link" @click="scrollTo('skills')">Skills</a>
    </div>
  </nav>
</template>

<script>
export default {
  name: "RokeNav",
  data() {
    return {
      onTop: true,
    };
  },
  methods: {
    handleScroll() {
      this.onTop = window.pageYOffset === 0;
    },
    scrollTo(id = undefined) {
      const headerOffset = 100;
      const elementPosition = id
        ? document.getElementById(id).getBoundingClientRect().top - headerOffset
        : 0;

      window.scrollTo({ top: elementPosition, behavior: "smooth" });
    },
  },
  created: function () {
    window.addEventListener("scroll", this.handleScroll);
    window.addEventListener("hashchange", this.scrollTo);
  },
  destroyed: function () {
    window.removeEventListener("scroll", this.handleScroll);
    window.addEventListener("hashchange", this.scrollTo);
  },
};
</script>

<style lang="scss" scoped>
.nav {
  z-index: 100;
  position: fixed;
  padding: 30px;
  width: 100%;
  -webkit-transition: all 250ms ease-in-out;
  transition: all 250ms ease-in-out;

  &__logo {
    transition: transform 250ms ease-in-out;
    cursor: pointer;
    margin-right: 50px;
    opacity: 0.9;
  }

  &__container {
    display: flex;
    align-items: center;
  }

  &__link {
    padding: 15px;
    margin: 0 15px;
    text-decoration: none;
    cursor: pointer;
    box-sizing: border-box;

    &:hover {
      border-bottom: 3px solid black;
    }
  }

  h2 {
    display: inline-block;
    padding-right: 5rem;
  }

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }

  &--scrolled {
    background-color: white;
    box-shadow: 0 8px 32px 0 rgba(146, 146, 146, 0.37);
    padding: 5px 30px;

    .nav__logo {
      transform: scale(0.5, 0.5);
    }
  }
}
</style>
