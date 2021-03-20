<template>
  <div class="home">
    <roke-hero />
    <roke-skills />
    <img alt="Vue logo" src="../assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from "@/components/HelloWorld.vue";
import RokeHero from "@/components/RokeHero";
import RokeSkills from "@/components/RokeSkills";

export default {
  name: "Home",
  components: {
    RokeSkills,
    RokeHero,
    HelloWorld,
  },
};
</script>
