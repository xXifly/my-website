<template>
  <div class="about-me">
    <h1 class="about-me__title">{{ $t("aboutMe.title") }}</h1>
    <div class="about-me__content">
      <Skill
        v-for="item in skills"
        :key="item.code"
        :code="item.code"
        :name="item.name"
        :picture="item.picture"
        :color="item.color"
        :description="item.description"
      >
      </Skill>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Skill from "./Skill.vue";

export default Vue.extend({
  components: {
    Skill
  },
  data() {
    return {
      name: "AboutMe",
      skills: [
        {
          code: "ful" as String,
          name: this.$t("aboutMe.skills[0].title") as String,
          picture: "developer.svg" as String,
          description: this.$t("aboutMe.skills[0].description") as String
        },
        {
          code: "des" as String,
          name: this.$t("aboutMe.skills[1].title") as String,
          picture: "designer.svg" as String,
          description: this.$t("aboutMe.skills[1].description") as String
        },
        {
          code: "man" as String,
          name: this.$t("aboutMe.skills[2].title") as String,
          picture: "management.svg" as String,
          description: this.$t("aboutMe.skills[2].description") as String
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

.about-me {
  @include bloc($background-color);

  &__content {
    display: flex;

    @include responsive-under(laptop) {
      flex-direction: column;
      align-content: center;
      align-items: center;
    }
  }
}
</style>
