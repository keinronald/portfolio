<template>
  <footer class="container footer">
    <span>&copy; <strong>{{ currentYear }}</strong> Ronald Keinberger</span>
    <span>created with ❤️ and <a href="https://vuejs.org/" target="_blank" class="footer__link">Vue.js</a> - deployed by <a href="https://www.netlify.com/" target="_blank" class="footer__link">Netlify</a></span>
  </footer>
</template>

<script>
export default {
  name: "RokeFooter",
  computed: {
    currentYear() {
      return new Date().getFullYear();
    },
  },
};
</script>

<style lang="scss" scoped>
.footer {
  display: flex;
  justify-content: space-between;
  padding: 2rem 0;

  &__link {
    text-decoration: none;
    color: #42b983;
  }
}
</style>
