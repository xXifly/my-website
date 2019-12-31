<template>
  <div class="category">
    <div class="category__name">{{ name }}</div>
    <div class="category__content">
      <Techno
        v-for="item in techno"
        :key="item.name"
        :name="item.name"
        :rate="item.rate"
      />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import Techno from "./Techno.vue";

export default Vue.extend({
  name: "Card",
  components: {
    Techno
  },
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
@import "~/assets/scss/main.scss";

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
</style>
