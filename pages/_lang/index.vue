<template>
  <div class="container">
    <Home />
    <AboutMe />
    <Career />
    <Education />
    <Skills />
  </div>
</template>

<script>
import Home from "~/components/Home.vue";
import Career from "~/components/Career/Career.vue";
import AboutMe from "~/components/AboutMe/AboutMe.vue";
import Education from "~/components/Education/Education.vue";
import Skills from "~/components/Skills/Skills.vue";

export default {
  name: "index",
  components: {
    Home,
    Career,
    AboutMe,
    Education,
    Skills
  }
};
</script>

<style>
.container {
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
}
</style>
