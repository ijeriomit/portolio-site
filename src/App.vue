<template>
  <div id="app">
    <floating-header class="gradient header"></floating-header>
    <div class="content-grid">
      <div
        id="HOME"
        class="primary-background-block"
        style="grid-row: 1/1;"
      ></div>
      <div class="content-block" style="grid-row: 1/1;">
        <home class="section-wrapper" style="padding-bottom: 10vh;"></home>
      </div>
      <div
        id="ABOUT-ME"
        style=" grid-row: 2/2;"
        class="secondary-background-block"
      ></div>
      <div class="content-block" style="grid-row: 2/2;">
        <about class="section-wrapper"> </about>
      </div>
      <div
        id="WORK-EXPERIENCE"
        class="secondary-background-block"
        style="grid-row: 3/3;"
      ></div>
      <div class="content-block" style="grid-row: 3/3;">
        <workexp class="section-wrapper"></workexp>
      </div>
      <div
        id="PROJECTS"
        class="secondary-background-block"
        style="grid-row: 4/4;"
      ></div>
      <div class="content-block" style="grid-row: 4/4;">
        <projects class="section-wrapper"></projects>
      </div>
      <div
        id="CONTACT-ME"
        class="bottom-background-block"
        style="grid-row:5/5;"
      ></div>
      <div class="content-block" style="grid-row: 5/5;">
        <contact-me></contact-me>
      </div>
      <div class="footer" style="grid-row: 6/6;"></div>
    </div>
    <div class="social-bar"></div>
  </div>
</template>
<script>
import FloatingHeader from "./components/floating-header.vue";
import Home from "./sections/home.vue";
import AboutMe from "./sections/about-me.vue";
import workExperience from "./sections/work-experience.vue";
import projects from "./sections/projects.vue";
import contactMe from "./sections/contact-me.vue";

export default {
  name: "homepage",
  components: {
    "floating-header": FloatingHeader,
    home: Home,
    about: AboutMe,
    workexp: workExperience,
    projects: projects,
    "contact-me": contactMe
  }
};
</script>
<style lang="scss">
@import "@/scss/variables.scss";

#app {
  height: $section-height * 5 + $header-height + $footer-height;
  width: 100vw;
  position: relative;
}
.header {
  height: $header-height;
  position: fixed;
  z-index: 1000;
  background-color: $primary-color;
}
.footer {
  z-index: 1;
  position: relative;
  background-color: $primary-color;
  grid-column: 1/4;
}
.content-grid {
  position: relative;
  top: $header-height;
  height: $section-height * 5;
  width: inherit;
  display: grid;
  display: grid;
  grid-template-columns: 10vw 80vw 10vw;
  grid-template-rows: $section-height $section-height $section-height $section-height $section-height $footer-height;
}
html {
  scroll-behavior: smooth;
}
body {
  margin: 0px;
}
.background-block {
  z-index: 1;
  height: $section-height;
  position: relative;
  grid-column: 1/4;
  border: solid 2px red;
}
.content-block {
  z-index: 2;
  position: relative;
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
  justify-content: center;
  grid-column: 2/2;
}
.primary-background-block {
  @extend .background-block;
  color: $dark-text-color;
  background-color: $primary-color;
}
.bottom-background-block {
  @extend .primary-background-block;
  height: ($section-height / 2);
  align-self: end;
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
.section-wrapper {
  display: flex;
  flex-flow: column nowrap;
  max-height: $section-height;
}
</style>
