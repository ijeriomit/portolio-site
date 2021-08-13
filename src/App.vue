<template>
  <div id="app">
    <floating-header></floating-header>
    <div id="HOME" class="secondary-background-block"></div>
    <div id="ABOUT ME" class="primary-background-block"></div>
    <div id="WORK EXPERIENCE" class="secondary-background-block "></div>
    <div id="PROJECTS" class="primary-background-block"></div>
    <div id="HOBBIES" class="secondary-background-block"></div>
    <div id="CONTACT ME" class="primary-background-block"></div>
  </div>
</template>
<script>
import FloatingHeader from "./components/floating-header.vue";
export default {
  name: "homepage",
  components: {
    "floating-header": FloatingHeader
  }
};
</script>
<style lang="scss">
@import "@/scss/variables.scss";

#app {
  height: 4665px;
  width: 1920px;
}
html {
  scroll-behavior: smooth;
}

.background-block {
  width: 100%;
  height: 16.66666666%;
}
.primary-background-block {
  @extend .background-block;
  background-color: $primary-color;
  color: $light-text-color;
}
.secondary-background-block {
  @extend .background-block;
  background-color: $secondary-color;
  color: $dark-text-color;
}
</style>
