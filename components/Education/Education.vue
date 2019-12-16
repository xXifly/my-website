<template>
  <div class="education">
    <h1 class="education__title">Education</h1>
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
      degrees: [
        {
          name: "Diplome d'Ingénieur spécialité Informatique" as String,
          organism: "Ecole d'Ingénieurs du Littoral Côte d'Opale (EILCO)" as String,
          location: "Calais, France" as String,
          date: "2013 to 2019" as String
        }
      ]
    };
  }
});
</script>

<style lang="scss">
@import "~/assets/scss/utils/_variables.scss";
@import "~/assets/scss/utils/_mixins.scss";

$background-color: $white;

.education {
  @include bloc($background-color);
}
</style>
