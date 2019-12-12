<template>
  <div class="intro-panel">
    <div class="intro-panel__lang">
      <nuxt-link to="/fr">Fr</nuxt-link> / <nuxt-link to="/en">En</nuxt-link>
    </div>
    <img class="intro-panel__portrait" src="~assets/img/portrait.svg" />
    <div class="intro-panel__name">
      {{ $t("home.introduction") }}<span class="name">Alexandre</span>.
    </div>
    <div class="intro-panel__description">
      {{ $t("home.presentation1") }}{{ age }}{{ $t("home.presentation2") }}
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Home",
  computed: {
    age(): number {
      var today: Date = new Date();
      var birthDate: Date = new Date("01/25/1996");
      var age: number = today.getFullYear() - birthDate.getFullYear();
      var m: number = today.getMonth() - birthDate.getMonth();
      if (m < 0 || (m === 0 && today.getDate() < birthDate.getDate())) {
        age--;
      }
      return age;
    }
  }
});
</script>

<style lang="scss">
@import "~/assets/scss/utils/_variables.scss";

.intro-panel {
  background-color: $primary-color;
  padding: 5%;
  min-height: 75vh;
  position: relative;
  margin-bottom: 25vh;
  text-align: center;
  color: $white;

  &__lang {
    position: absolute;
    right: 40px;
    top: 30px;
    color: white;
    font-weight: bold;
    font-size: 18px;

    a {
      text-decoration: none;
      &:visited {
        color: $white;
      }
      &:hover {
        color: darken($white, 30%);
      }
    }
  }

  &__portrait {
    width: 200px;
  }

  &__name {
    display: block;
    font-size: 70px;
    letter-spacing: 1px;
    font-weight: 500;
    font-family: Woodchuck-Regular;

    .name {
      color: $secondary-color;
    }
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
    border-top: solid 50px $primary-color;
    border-left: solid 50px transparent;
    border-right: solid 50px transparent;
    margin-left: -50px;
  }
}
</style>
