<template>
  <div class="container">
    <Home />
    <AboutMe />
    <Career />
  </div>
</template>

<script>
import Home from "~/components/Home.vue";
import Career from "~/components/Career/Career.vue";
import AboutMe from "~/components/AboutMe/AboutMe.vue";

export default {
  name: "index",
  components: {
    Home,
    Career,
    AboutMe
  }
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 200vh;
  display: flex;
  flex-direction: column;
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
}
</style>
