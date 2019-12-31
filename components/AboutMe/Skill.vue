<template>
  <div class="skill">
    <div class="skill__img-content">
      <img
        aria-hidden="true"
        class="skill__img"
        :src="`/img/${picture}`"
      />
    </div>
    <h1 :class="`skill__title skill__title--${code}`">{{ name }}</h1>
    <div class="skill__description" v-for="item in description" :key="item">
      {{ item }}
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Skill",
  props: {
    name: {
      type: String,
      required: true
    },
    picture: {
      type: String,
      required: true
    },
    code: {
      type: String,
      required: true
    },
    description: {
      type: Array,
      required: true
    }
  }
});
</script>

<style lang="scss">
@import "~/assets/scss/main.scss";

.skill {
  @include bordered-box;
  padding: $card-padding;
  display: flex;
  flex-direction: column;
  text-align: center;
  margin: 3%;
  width: 33%;
  @include responsive-under(laptop) {
    width: 67%;
  }
  @include responsive-under(mobile) {
    width: 100%;
  }

  &__img {
    width: 75%;
    max-width: 225px;
    margin-top: 25px;
  }

  &__title {
    font-family: Woodchuck-Regular;
    font-size: 40px;
    margin: 25px 0 10px 0;
    @include skill-color($skill-color);
  }

  &__description {
    text-align: justify;
    margin: 10px 0;
  }
}
</style>
