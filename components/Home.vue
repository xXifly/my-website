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
    <div class="intro-panel__network">
      <a href="https://www.linkedin.com/in/alexandre-joron-797460a8">
        <fa :icon="['fab', 'linkedin']" />
      </a>
      <a href="https://github.com/xXifly">
        <fa :icon="['fab', 'github']" />
      </a>
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


.intro-panel {
  background-color: $primary-color;
  padding: 5%;
  min-height: 75vh;
  position: relative;
  margin-bottom: 25vh;
  text-align: center;
  color: $white;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;

  &__lang {
    position: absolute;
    right: 40px;
    top: 30px;
    color: white;
    font-weight: bold;
    font-size: 18px;
  }

  a {
    color: $white;
    text-decoration: none;
    &:visited, &:active {
      color: $white;
    }
    &:hover {
      color: darken($white, 30%);
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
    @include responsive-under(mobile) {
      font-size: 50px;
    }
    .name {
      color: $secondary-color;
    }
  }

  &__description {
    font-size: 25px;
    word-spacing: 5px;
    font-weight: 300;
    @include responsive-over(mobile) {
      width: 41%;
    }
  }

  &__network {
    font-size: 35px;
  }

  &::after {
    @include array(50px, $primary-color, bottom);
    top: 98.1%;
    left: 50%;
  }
}
</style>
