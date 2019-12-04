<template>
  <div class="about-me">
    <h1 class="about-me__title">About Me</h1>
    <div class="about-me__content">
      <Skill
        v-for="item in skills"
        :key="item.name"
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
          name: "FullStack Developer",
          picture: "",
          color: "blue",
          description: [
            "Invested in all layers of development, I like to create the most optimized, ordered and efficient code."
          ]
        },
        {
          name: "Designer",
          picture: "designer.svg",
          color: "yellow",
          description: [
            "Passionate about art, design and graphics, I strive to create the best UX/UI interface.",
            "I use my own style to design logos, icons and graphics to create an unique application."
          ]
        },
        {
          name: "Management skills",
          picture: "management.svg",
          color: "red",
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
@import "~/assets/scss/utils/variables.scss";
@import "~/assets/scss/utils/_mixins.scss";

.about-me {
  min-height: 100vh;

  &__title {
    @include bloc-title($primary-color);
  }

  &__content {
    display: flex;
  }
}
</style>
