<template>
  <div class="experience">
    <span class="circle" />

    <div class="experience__title">
      <span class="company">{{ company.toUpperCase() }}</span> |
      <span class="post">{{ post }}</span>
    </div>
    <div class="experience__subtitle">
      <span class="experience__date">{{ startDate }} to {{ endDate }}</span>
      <span class="experience__location">
        <fa :icon="['fas', 'map-marker-alt']" /> {{ location }}
      </span>
    </div>
    <div class="experience__description">{{ description }}</div>
  </div>
</template>

<script>
export default {
  name: "Experience",
  props: {
    post: {
      type: String,
      required: true
    },
    company: {
      type: String,
      required: true
    },
    location: {
      type: String,
      required: true
    },
    startDate: {
      type: String,
      required: true
    },
    endDate: {
      type: String,
      default: "now"
    },
    description: {
      type: String,
      required: true
    }
  }
};
</script>

<style lang="scss">
$primary-color: #11467f;
$secondary-color: #f9af3b;
$back-color: #ffffff;
$border-color: #cfdae5;
$circle-size: 51px;
$array-size: 12px;

.experience {
  padding: 15px;
  border-radius: 17px;
  margin: 15px auto;
  position: relative;
  background-color: $back-color;
  border: 9px solid $border-color;
  box-shadow: 10px 5px 5px darken($primary-color, 5%);
  transition: transform ease-in-out 400ms;
  transform-origin: -84px 50%;
  &:hover {
    transform: scale(1.04);
  }

  &__title {
    font-size: 19px;
    font-weight: bold;
    color: $primary-color;
  }

  &__subtitle {
    display: flex;
    justify-content: space-between;
    margin: 5px 0;
  }

  &__location {
    color: darken($secondary-color, 12%);
    font-weight: 600;
  }

  &__date {
    color: #757575;
  }

  &__description {
    text-align: justify;
  }

  &::after {
    content: "";
    height: 0;
    width: 0;
    display: block;
    position: absolute;
    top: 50%;
    border-right: solid $array-size $back-color;
    border-top: solid $array-size transparent;
    border-bottom: solid $array-size transparent;
    margin-top: -$array-size;
    left: -$array-size;
  }

  &::before {
    content: "";
    height: 0;
    width: 0;
    display: block;
    position: absolute;
    top: 50%;
    border-right: solid $array-size + 9 $border-color;
    border-top: solid $array-size + 9 transparent;
    border-bottom: solid $array-size + 9 transparent;
    margin-top: -($array-size + 9);
    left: -($array-size + 9);
  }

  .circle {
    background-color: $back-color;
    border: 9px solid $border-color;
    width: $circle-size;
    height: $circle-size;
    border-radius: $circle-size / 2;
    display: block;
    position: absolute;
    margin-top: -$circle-size / 2;
    left: -84px - $circle-size / 2;
    top: 50%;
  }
}
</style>
