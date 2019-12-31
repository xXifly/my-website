<template>
  <div class="education">
    <h1 class="education__title">{{ $t("education.title") }}</h1>
    <div class="education__content">
      <Card
        v-for="item in degrees"
        :key="item.name"
        :name="item.name"
        :organism="item.organism"
        :location="item.location"
        :date="item.date"
      />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Card from "./Card.vue";

export default Vue.extend({
  components: {
    Card
  },
  data() {
    return {
      name: "Education",
      degrees: this.$t("education.degrees")
    };
  }
});
</script>

<style lang="scss">
@import "~/assets/scss/main.scss";

$background-color: $white;

.education {
  @include bloc($background-color);

  &__content {
    margin: 100px 0;
  }
}
</style>
