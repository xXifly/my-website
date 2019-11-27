<template>
  <div class="home">
    <div class="blue-panel">
      <img class="portrait" src="~assets/portrait.svg" />
      <div class="name">Hi, I'm Alexandre.</div>
      <div class="description">
        I'm a 23-year-old web developer passionate about full-stack web
        development, design and graphics.
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({});
</script>

<style land="scss" scoped>
.home {
  height: 100vh;
}

.blue-panel {
  background-color: #11467f;
  padding: 5%;
  height: 75vh;
  position: relative;
}

.blue-panel::after {
  content: "";
  height: 0;
  width: 0;
  display: block;
  position: absolute;
  top: 98.1%;
  left: 70%;
  border-top: solid 50px #11467f;
  border-left: solid 50px transparent;
  border-right: solid 50px transparent;
  margin-left: -25%;
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
