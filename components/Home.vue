<template>
  <div class="home">
    <img class="portrait" src="~assets/portrait.svg" />
    <div class="name">Hi, I'm Alexandre.</div>
    <div class="description">
      I'm a 23-year-old web developer passionate aboute full-stack web development,
      design and graphics.
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({});
</script>

<style land="scss" scoped>
.home {
  background-color: #11467f;
  width: 100%;
  padding: 5%;
}

.portrait {
  width: 200px;
}

.name {
  font-family: "Quicksand", "Source Sans Pro", -apple-system, BlinkMacSystemFont,
    "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 70px;
  color: #ffffff;
  letter-spacing: 1px;
}

.description {
  font-weight: 300;
  font-size: 25px;
  color: #ffffff;
  word-spacing: 5px;
  width: 41%;
  margin: auto;
}
</style>
