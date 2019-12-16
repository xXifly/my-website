<template>
  <div class="card">
    <div class="card__picture-content">
      <img class="card__picture" src="~/assets/img/degree.svg" />
    </div>
    <div class="card__description-content">
      <div class="card__title">
        {{ name }}
      </div>

      <div class="card__information">
        <span class="card__date">{{ date }}</span>
        <span class="card__location">
          {{ location }} <fa :icon="['fas', 'map-marker-alt']" />
        </span>
      </div>

      <div class="card__organism">
        {{ organism }}
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Card",
  props: {
    name: {
      type: String,
      required: true
    },
    organism: {
      type: String,
      required: true
    },
    location: {
      type: String,
      required: true
    },
    date: {
      type: String,
      required: true
    }
  }
});
</script>

<style lang="scss">
@import "~/assets/scss/utils/_variables.scss";
@import "~/assets/scss/utils/_mixins.scss";

$background-color: $white;

.card {
  @include bordered-box;
  @include information-card;
  display: flex;
  align-items: center;
  width: max-content;
  margin: 3% auto;
  max-width: 100%;
  @include responsive-under(tablet) {
    flex-direction: column;
  }

  &__picture {
    width: 300px;
  }

  &__picture-content {
    text-align: center;
    padding: $card-padding;
    @include responsive-over(tablet) {
      border-right: $border-size solid $border-color;
    }
  }

  &__description-content {
    padding: $card-padding;
  }
}
</style>
