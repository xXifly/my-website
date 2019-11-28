<template>
  <div class="intro-panel">
    <img class="intro-panel__portrait" src="~assets/portrait.svg" />
    <div class="intro-panel__name">Hi, I'm Alexandre.</div>
    <div class="intro-panel__description">
      I'm a {{ age }}-year-old web developer passionate aboute full-stack web
      development, design and graphics.
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Home",
  computed: {
    age() {
      var today = new Date();
      var birthDate = new Date("01/25/1996");
      var age = today.getFullYear() - birthDate.getFullYear();
      var m = today.getMonth() - birthDate.getMonth();
      if (m < 0 || (m === 0 && today.getDate() < birthDate.getDate())) {
        age--;
      }
      return age;
    }
  }
});
</script>

<style lang="scss">
$colour-primary: #11467f;

.intro-panel {
  background-color: $colour-primary;
  padding: 5%;
  min-height: 75vh;
  position: relative;
  margin-bottom: 25vh;
  text-align: center;
  color: #ffffff;

  &__portrait {
    width: 200px;
  }

  &__name {
    display: block;
    font-size: 70px;
    letter-spacing: 1px;
    font-weight: 500;
  }

  &__description {
    font-size: 25px;
    word-spacing: 5px;
    width: 41%;
    margin: auto;
    font-weight: 300;
  }

  &::after {
    content: "";
    height: 0;
    width: 0;
    display: block;
    position: absolute;
    top: 98.1%;
    left: 50%;
    border-top: solid 50px $colour-primary;
    border-left: solid 50px transparent;
    border-right: solid 50px transparent;
    margin-left: -50px;
  }
}
</style>
