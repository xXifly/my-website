<template>
  <div class="skill">
    <div class="skill__picture-content">
      <img src="" alt="" />
    </div>
    <h1 class="skill__title">{{ name }}</h1>
    <div>
      Passionate about art, design and graphics, I strive to create the best
      UX/UI interface.
    </div>
    <div>
      I use my own style to design logos, icons and graphics to create an unique
      application.
    </div>
  </div>
</template>

<script>
export default {
  name: "Skill",
  props: {
    name: {
      type: String,
      required: true
    },
    picture: {
      type: String,
      required: true
    },
    description: {
      type: String,
      required: true
    }
  }
};
</script>

<style lang="scss">
.skill {
  display: flex;
  flex-direction: column;
  width: 33%;
  text-align: center;
  margin: 3%;
  padding: 3%;
  border: 1px solid;
  border-radius: 15px;

  &__title {
    font-family: Woodchuck-Regular;
    font-size: 40px;
  }
}
</style>
