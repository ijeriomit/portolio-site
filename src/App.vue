<template>
  <div id="app">
    <floating-header
      class="gradient"
      style="height: 50px z-index: 1000;"
    ></floating-header>
    <div id="HOME" class="primary-background-block">
      <home></home>
    </div>
    <div
      id="ABOUT-ME"
      style="justify-content: center;"
      class="secondary-background-block"
    >
      <about> </about>
    </div>
    <div id="WORK-EXPERIENCE" class="secondary-background-block ">
      <workexp></workexp>
    </div>
    <div id="PROJECTS" class="secondary-background-block">
      <projects></projects>
    </div>
    <div id="CONTACT-ME" class="primary-background-block"></div>
    <div class="social-bar"></div>
  </div>
</template>
<script>
import FloatingHeader from "./components/floating-header.vue";
import Home from "./sections/home.vue";
import AboutMe from "./sections/about-me.vue";
import workExperience from "./sections/work-experience.vue";
import projects from "./sections/projects.vue";

export default {
  name: "homepage",
  components: {
    "floating-header": FloatingHeader,
    home: Home,
    about: AboutMe,
    workexp: workExperience,
    projects: projects
  }
};
</script>
<style lang="scss">
@import "@/scss/variables.scss";

$site-width: 1920px;
$background-block-height: 900px;
#app {
  height: $background-block-height * 5;
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
  z-index: 1;
  height: $background-block-height;
  position: relative;
  top: 70px;
  // left: 0;
  display: flex;
  flex-flow: row nowrap;
}
.primary-background-block {
  @extend .background-block;
  color: $dark-text-color;
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
  color: $primary-color;
}
</style>
