<template>
  <div class="footer">
    <div>© Alexandre Joron 2019</div>
    <div class="footer__text">
      Made with <fa :icon="['fas', 'coffee']" /> and
      <fa :icon="['fas', 'heart']" />.
    </div>
    <div>
      <a href="https://github.com/xXifly/my_personal_website">
        < Code Source />
      </a>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from "vue";

export default Vue.extend({});
</script>

<style lang="scss">
@import "~/assets/scss/main.scss";

$background-color: $primary-color;

.footer {
  background-color: #262626;
  color: #d0d0d0;
  @include flex(row);
  justify-content: space-between;
  padding: 30px;

  a,
  a:active,
  a:visited {
    color: #d0d0d0;
    text-decoration: none;
  }

  a:hover {
      color: darken(#d0d0d0, 10%);
  }
}
</style>
