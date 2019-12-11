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

<script>
import Card from "./Card.vue";

export default {
  components: {
    Card
  },
  data() {
    return {
      name: "Education",
      degrees: [
        {
          name: "Diplome d'Ingénieur spécialité Informatique",
          organism: "Ecole d'Ingénieurs du Littoral Côte d'Opale (EILCO)",
          location: "Calais, France",
          date: "2013 to 2019"
        }
      ]
    };
  }
};
</script>

<style lang="scss">
@import "~/assets/scss/utils/_variables.scss";
@import "~/assets/scss/utils/_mixins.scss";

$background-color: $white;

.education {
  @include bloc($background-color);
}
</style>
