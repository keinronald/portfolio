<template>
  <div id="app">
    <roke-nav />
    <router-view />
    <roke-footer />
  </div>
</template>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
</style>

<script>
import RokeNav from "@/components/RokeNav";
import RokeFooter from "@/components/RokeFooter";
export default {
  components: { RokeFooter, RokeNav },
};
</script>
