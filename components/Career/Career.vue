<template>
  <div class="career">
    <h1 class="career__title">{{ $t("career.title") }}</h1>
    <div class="career__content">
      <div class="career__picture-content">
        <img class="career__picture" src="~/assets/img/career.svg" />
      </div>
      <div class="career__list">
        <Experience
          v-for="item in experiences"
          :key="item.post"
          :post="item.post"
          :company="item.company"
          :location="item.location"
          :date="item.date"
          :description="item.description"
          :objective="item.objective"
          :environment="item.environment"
        />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Experience from "./Experience.vue";

export default Vue.extend({
  components: {
    Experience
  },
  data() {
    return {
      name: "career",
      experiences: this.$t("career.experiences")
    };
  }
});
</script>

<style lang="scss">
@import "~/assets/scss/utils/_variables.scss";
@import "~/assets/scss/utils/_mixins.scss";

$background-color: $primary-color;

.career {
  @include bloc($background-color);

  &__content {
    display: flex;
    align-items: center;
    margin-top: 3%;
    @include responsive-under(tablet) {
      flex-direction: column;
    }
  }

  &__picture-content {
    width: 36%;
    @include responsive-under(tablet) {
      width: 60%;
    }
  }

  &__picture {
    width: 100%;
  }

  &__list {
    margin: auto;
    width: 70%;
    @include responsive-over(tablet) {
      padding-left: 71px;
      border-left: 9px solid $border-color;
      width: 55%;
    }
  }
}
</style>
