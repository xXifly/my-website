<template>
  <div class="about-me">
    <h1 class="about-me__title">About Me</h1>
    <div class="about-me__content">
      <Skill
        v-for="item in skills"
        :key="item.name"
        :name="item.name"
        :picture="item.picture"
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
          description: ""
        },
        {
          name: "Designer",
          picture: "",
          description: ""
        },
        {
          name: "Management skills",
          picture: "",
          description: ""
        }
      ]
    };
  }
};
</script>

<style lang="scss">
$primary-color: #11467f;

.about-me {
  min-height: 100vh;

  &__title {
    text-align: center;
    font-size: 110px;
    color: $primary-color;
    margin: 0 0 20px 0;
    font-family: Woodchuck-Regular;
    letter-spacing: 3px;
  }

  &__content {
    display: flex;
  }
}
</style>
