<template>
    <div class="techno">
    <div class="techno__bar" :style="`width:${rate}%`">
        <div class="techno__name">{{ name }}</div>
    </div>
    <div class="techno__rate">{{ rate }}%</div>
    </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({
  name: "Card",
  props: {
    name: {
      type: String,
      required: true
    },
    rate: {
      type: Number,
      required: true
    }
  }
});
</script>

<style lang="scss">
@import "~/assets/scss/main.scss";

.techno {
  background-color: #ddd;
  margin: 3px;
  position: relative;
  border-radius: 5px;

  &__bar {
    background-color: $secondary-color;
    border-radius: 5px;
  }

  &__name {
    padding: 10px;
    font-weight: 600;
  }

  &__rate {
    position: absolute;
    right: 10px;
    top: 0;
    line-height: 35px;
    color: rgba(0, 0, 0, 0.6);
  }
}
</style>
