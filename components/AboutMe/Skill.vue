<template>
  <div class="skill">
    <div class="skill__img-content">
      <img class="skill__img" :src="`img/${picture}`" alt="" />
    </div>
    <h1 :class="`skill__title skill__title--${color}`">{{ name }}</h1>
    <div class="skill__description" v-for="item in description" :key="item">
      {{ item }}
    </div>
  </div>
</template>

<script>
export default {
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
    color: {
      type: String,
      required: true
    },
    description: {
      type: Array,
      required: true
    }
  }
};
</script>

<style lang="scss">
@import "~/assets/scss/utils/variables.scss";
@import "~/assets/scss/utils/_mixins.scss";

.skill {
  @include bordered-box;
  display: flex;
  flex-direction: column;
  width: 33%;
  text-align: center;
  margin: 3%;

  &__img {
    width: 75%;
    max-width: 225px;
    margin-top: 25px;
  }

  &__title {
    font-family: Woodchuck-Regular;
    font-size: 40px;
    margin: 25px 0 10px 0;
  }

  &__title--red {
    color: #ff3939;
  }

  &__title--blue {
    color: lighten($primary-color, 20%);
  }

  &__title--yellow {
    color: $secondary-color;
  }

  &__description {
    text-align: justify;
    margin: 10px;
  }
}
</style>
