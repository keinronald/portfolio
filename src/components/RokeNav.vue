<template>
  <nav class="nav" :class="{ 'nav--scrolled': !onTop }">
    <div class="container">
      <h2>RK-logo</h2>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
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
  },

  created: function () {
    window.addEventListener("scroll", this.handleScroll);
  },
  destroyed: function () {
    window.removeEventListener("scroll", this.handleScroll);
  },
};
</script>

<style lang="scss" scoped>
.nav {
  position: fixed;
  padding: 30px;
  width: 100%;
  -webkit-transition: all 250ms ease-in-out;
  transition: all 250ms ease-in-out;

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
  }
}
</style>
