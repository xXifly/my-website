<template>
  <div class="about-me">
    <h1 class="about-me__title">About Me</h1>
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
          name: "FullStack Developer",
          picture: "",
          description: [
            "Invested in all layers of development, I like to create the most optimized, ordered and efficient code."
          ]
        },
        {
          code: "des",
          name: "Designer",
          picture: "designer.svg",
          description: [
            "Passionate about art, design and graphics, I strive to create the best UX/UI interface.",
            "I use my own style to design logos, icons and graphics to create an unique application."
          ]
        },
        {
          code: "man",
          name: "Management skills",
          picture: "management.svg",
          description: [
            "Accustomed to working in a team, I have a good understanding of the Agile method and good knowledge of project and team management.",
            "I am naturally sociable and enjoy human contact. I use this to improve the productivity of my projects because together we go further."
          ]
        }
      ]
    };
  }
};
</script>

<style lang="scss">
@import "~/assets/scss/utils/_variables.scss";
@import "~/assets/scss/utils/_mixins.scss";

.about-me {
  min-height: 100vh;

  &__title {
    @include bloc-title($primary-color);
  }

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
