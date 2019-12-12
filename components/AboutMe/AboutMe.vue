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

<script>
import Skill from "./Skill.vue";

export default {
  components: {
    Skill
  },
  data() {
    return {
      name: "AboutMe",
      skills: [
        {
          code: "ful",
          name: this.$t("aboutMe.skills[0].title"),
          picture: "",
          description: this.$t("aboutMe.skills[0].description")
        },
        {
          code: "des",
          name: this.$t("aboutMe.skills[1].title"),
          picture: "designer.svg",
          description: this.$t("aboutMe.skills[1].description")
        },
        {
          code: "man",
          name: this.$t("aboutMe.skills[2].title"),
          picture: "management.svg",
          description: this.$t("aboutMe.skills[2].description")
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
