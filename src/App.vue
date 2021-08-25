<template>
  <div id="app">
    <floating-header
      class="gradient"
      style="height: 50px z-index: 1000;"
    ></floating-header>
    <div style="top: 67px;" id="HOME" class="primary-background-block">
      <home></home>
    </div>
    <div id="ABOUT ME" class="secondary-background-block">
      <about> </about>
    </div>
    <div id="WORK EXPERIENCE" class="primary-background-block "></div>
    <div id="PROJECTS" class="secondary-background-block"></div>
    <div id="HOBBIES" class="primary-background-block"></div>
    <div id="CONTACT ME" class="secondary-background-block"></div>
  </div>
</template>
<script>
import FloatingHeader from "./components/floating-header.vue";
import Home from "./sections/home.vue";
import AboutMe from "./sections/about-me.vue";

export default {
  name: "homepage",
  components: {
    "floating-header": FloatingHeader,
    home: Home,
    about: AboutMe
  }
};
</script>
<style lang="scss">
@import "@/scss/variables.scss";

$site-width: 1920px;
#app {
  height: 4665px;
  width: 1920px;
  display: flex;
  flex-flow: column nowrap;
  max-width: 1920px;
  position: relative;
  left: 0;
}
html {
  scroll-behavior: smooth;
}

.background-block {
  width: 100vw;
  z-index: -1;
  height: 16.66666666%;
  position: relative;
  top: 70px;
  left: 0;
}
.primary-background-block {
  @extend .background-block;
  // @extend .gradient;
  color: $light-text-color;
  background-color: $primary-color;
}
.gradient {
  background-image: linear-gradient(
    to right,
    $secondary-color,
    #5db191,
    #197a55,
    $primary-color,
    $primary-color,
    $primary-color,
    #197a55,
    #5db191,
    $secondary-color
  );
}
.secondary-background-block {
  @extend .background-block;
  background-color: $secondary-color;

  color: $dark-text-color;
}
</style>
