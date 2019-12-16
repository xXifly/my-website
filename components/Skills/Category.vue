<template>
  <div class="category">
    <div class="category__name">{{ name }}</div>
    <div class="category__content">
      <div class="techno" v-for="item in techno" :key="item.name">
        <div class="techno__bar" :style="`width:${item.rate}%`">
          <div class="techno__name">{{ item.name }}</div>
        </div>
        <div class="techno__rate">{{ item.rate }}%</div>
      </div>
    </div>
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
    techno: {
      type: Array,
      required: true
    }
  }
});
</script>

<style lang="scss">
@import "~/assets/scss/utils/_variables.scss";
@import "~/assets/scss/utils/_mixins.scss";

.category {
  margin: 1%;
  width: 30%;
  min-width: 280px;

  &__name {
    font-weight: 600;
    font-size: 20px;
  }

  &__content {
    @include flex(column);
    justify-content: center;
    width: 100%;
  }
}

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
    width: 10vh;
    border-radius: 5px 0 0 5px;
  }

  &__rate {
    position: absolute;
    right: 10px;
    top: 0;
    height: 35px;
    line-height: 35px;
    color: rgba(0, 0, 0, 0.4);
  }
}
</style>
