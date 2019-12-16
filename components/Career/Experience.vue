<template>
  <div class="experience">
    <span class="circle" />

    <div class="experience__title">
      <span class="company">{{ company.toUpperCase() }}</span> |
      <span class="post">{{ post }}</span>
    </div>
    <div class="experience__information">
      <span class="experience__date">{{ date }}</span>
      <span class="experience__location">
        {{ location }} <fa :icon="['fas', 'map-marker-alt']" />
      </span>
    </div>
    <div class="experience__content">
      <div class="experience__description">{{ description }}</div>
      <div class="experience__objective">
        <strong>Objective :</strong> {{ objective }}
      </div>
      <div class="experience__environment">
        <strong>Technical environment :</strong> {{ environment }}
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Experience",
  props: {
    post: {
      type: String,
      required: true
    },
    company: {
      type: String,
      required: true
    },
    location: {
      type: String,
      required: true
    },
    date: {
      type: String,
      default: "now"
    },
    description: {
      type: String,
      required: true
    },
    objective: {
      type: String,
      required: true
    },
    environment: {
      type: String,
      required: true
    }
  }
});
</script>

<style lang="scss">
@import "~/assets/scss/utils/_variables.scss";
@import "~/assets/scss/utils/_mixins.scss";

$background-color: $primary-color;

.experience {
  @include bordered-box;
  @include information-card;
  padding: $card-padding;
  box-shadow: 10px 5px 5px darken($background-color, 5%);
  margin: 15px auto;
  position: relative;
  transform-origin: -84px 50%;

  &__content {
    text-align: justify;
  }

  @include responsive-over(tablet) {
    &::after {
      @include array($array-size, $white, left);
      top: 50%;
      left: -$array-size;
    }

    &::before {
      @include array($array-size + $border-size, $border-color, left);
      top: 50%;
      left: -($array-size + $border-size);
    }

    .circle {
      @include circle;
      left: -71px - $circle-size / 2 - $border-size - $border-size / 2;
      top: 50%;
    }
    .lol{
      left: -84px - $circle-size / 2;
      top: 50%;
    }
  }
}
</style>
