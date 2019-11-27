<template>
  <div class="container">
    <Home />
  </div>
</template>

<script>
import Home from "~/components/Home.vue";

export default {
  components: {
    Home
  }
};
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  text-align: center;
}
</style>
