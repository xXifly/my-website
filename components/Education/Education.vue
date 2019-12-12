<template>
  <div class="education">
    <h1 class="education__title">Education</h1>

    <Card
      v-for="item in degrees"
      :key="item.name"
      :name="item.name"
      :organism="item.organism"
      :location="item.location"
      :date="item.date"
    />
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
          name: "Diplome d'Ingénieur spécialité Informatique" as string,
          organism: "Ecole d'Ingénieurs du Littoral Côte d'Opale (EILCO)" as string,
          location: "Calais, France" as string,
          date: "2013 to 2019" as string
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
