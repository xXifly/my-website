<template>
  <div class="skills">
    <h1 class="skills__title">{{ $t("skills.title") }}</h1>
    <div class="skills__content">
      <div class="group" v-for="group in skills" :key="group.name">
        <div class="group__name">{{ group.name.toUpperCase() }}</div>
        <div class="group__content">
          <Category
            v-for="category in group.category"
            :key="category.name"
            :name="category.name"
            :techno="category.techno"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Category from "./Category.vue";

export default Vue.extend({
  components: {
    Category
  },
  data() {
    return {
      name: "skills",
      skills: [
        {
          name: "Front-End",
          category: [
            {
              name: this.$t("skills.languages"),
              techno: [
                { name: "HTML", rate: 90 },
                { name: "CSS", rate: 90 },
                { name: "JavaScript", rate: 70 },
                { name: "TypeScript", rate: 60 }
              ]
            },
            {
              name: "Frameworks",
              techno: [
                { name: "Angular", rate: 60 },
                { name: "Vue", rate: 70 },
                { name: "React", rate: 50 },
                { name: "Aurelia", rate: 60 }
              ]
            },
            {
              name: "CSS Technologies",
              techno: [
                { name: "SASS", rate: 70 },
                { name: "BootStrap", rate: 90 }
              ]
            }
          ]
        },
        {
          name: "Back-End",
          category: [
            {
              name: this.$t("skills.languages"),
              techno: [
                { name: "TypeScript", rate: 60 },
                { name: "Java", rate: 50 },
                { name: "C#", rate: 40 }
              ]
            },
            {
              name: "Backend technologies",
              techno: [
                { name: "Node.js", rate: 60 },
                { name: "Express", rate: 50 }
              ]
            }
          ]
        },
        {
          name: "Design",
          category: [
            {
              name: this.$t("skills.software"),
              techno: [
                { name: "Photoshop", rate: 70 },
                { name: "Illustrator", rate: 60 },
                { name: "Inkscape", rate: 80 }
              ]
            }
          ]
        }
      ]
    };
  }
});
</script>

<style lang="scss">
@import "~/assets/scss/main.scss";

$background-color: $primary-color;

.skills {
  @include bloc($background-color);
  color: $white;
}

.group {
  margin-bottom: 25px;

  &__name {
    position: relative;
    font-size: 24px;
    font-weight: bold;
    border-bottom: $border-size solid #cfdae5;
    padding-left: 60px;
    padding-bottom: 3px;

    &::before {
      content: "";
      @include circle;
      bottom: 0 - $circle-size / 2 - $border-size / 2;
      left: -2px;
    }
  }

  &__content {
    @include flex(row);
    margin-left: 50px;
  }
}
</style>
