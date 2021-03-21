<template>
  <div class="home">
    <roke-hero />
    <roke-skills id="skills" />
    <roke-form />
  </div>
</template>

<script>
// @ is an alias to /src
import RokeHero from "@/components/RokeHero";
import RokeSkills from "@/components/RokeSkills";
import RokeForm from "@/components/RokeForm";

export default {
  name: "Home",
  components: {
    RokeForm,
    RokeSkills,
    RokeHero,
  },
};
</script>
