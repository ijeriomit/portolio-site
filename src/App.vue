<template>
  <div id="app">
    <floating-header
      :tabs="[
        homeSection,
        aboutMeSection,
        workExpSection,
        projectSection,
        contactSection
      ]"
      class="header"
    ></floating-header>
    <div class="content-grid">
      <div class="primary-background-block" style="grid-row: 1/1;"></div>
      <div :id="homeSection.id" class="content-block" style="grid-row: 1/1;">
        <home class="section-wrapper" style="padding-bottom: 10vh;"></home>
      </div>
      <div
        style=" grid-row: 2/2; justify-content: center;"
        class="secondary-background-block"
      >
        <img style=" width: 700px; align-self: flex-end;" :src="mattFarImg" />
      </div>
      <div
        v-show="true"
        :id="aboutMeSection.id"
        class="content-block"
        style="grid-row: 2/2;"
      >
        <about class="section-wrapper"> </about>
      </div>
      <div
        class="primary-background-block"
        style="grid-row: 3/3; justify-content: flex-start;"
      >
        <img class="gear-image" :src="gearsImg" />
      </div>
      <div
        v-show="true"
        :id="workExpSection.id"
        class="content-block"
        style="grid-row: 3/3;"
      >
        <workexp class="section-wrapper"></workexp>
      </div>
      <div
        class="secondary-background-block"
        style="grid-row: 4/4;  border-bottom-width: 15px;"
      ></div>
      <div
        v-show="true"
        :id="projectSection.id"
        class="content-block"
        style="grid-row: 4/4;"
      >
        <projects class="section-wrapper"></projects>
      </div>
      <div
        class="primary-background-block"
        style="grid-row:5/5; align-self: flex-start; background-color: #008753; border:none; "
      >
        <img :src="phoneImg" />
      </div>
      <div
        v-show="true"
        :id="contactSection.id"
        class="content-block"
        style="grid-row: 5/5; flex-flow: column nowrap;"
      >
        <section-title>
          <template v-slot:section-title-content>
            <div class="section-title-keyword-1-alt">await</div>
            <div class="section-title-keyword-2-alt">fetch</div>
            <div class="section-title-operator-alt">(</div>
            <div class="section-title-title-alt">Contact Me</div>
            <div class="section-title-operator-alt">)</div>
          </template>
        </section-title>
        <contact-me class="section-wrapper"></contact-me>
      </div>
      <div class="footer" style="grid-row: 6/6;"></div>
      <div class="content-block" style="grid-row: 6/6">
        <Footer :footerIcons="footerIcons" class="section-wrapper"></Footer>
      </div>
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
import Footer from "./components/footer.vue";
import gears from "@/assets/clip-art-images/single-gear.png";
import mattFar from "@/assets/clip-art-images/Mattfarley-background.svg";
import phone from "@/assets/clip-art-images/phone.svg";
import mediumIcon from "@/assets/link-images/medium.png";
import githubIcon from "@/assets/link-images/github.svg";
import linkedinIcon from "@/assets/link-images/linkedinpng.svg";
import sectionTitle from "@/components/section-title.vue";

export default {
  name: "homepage",
  components: {
    "floating-header": FloatingHeader,
    home: Home,
    about: AboutMe,
    workexp: workExperience,
    projects: projects,
    "contact-me": contactMe,
    Footer: Footer,
    "section-title": sectionTitle
  },
  data: function() {
    return {
      gearsImg: gears,
      mattFarImg: mattFar,
      phoneImg: phone,
      homeSection: { link: "#HOME", text: ".home()", id: "HOME" },
      aboutMeSection: { link: "#ABOUTME", text: ".aboutMe()", id: "ABOUTME" },
      workExpSection: {
        link: "#WORKEXP",
        text: ".workExperience()",
        id: "WORKEXP"
      },
      projectSection: {
        link: "#PROJECTS",
        text: ".projects()",
        id: "PROJECTS"
      },
      contactSection: {
        link: "#CONTACTME",
        text: ".contactMe()",
        id: "CONTACTME"
      },
      footerIcons: [
        {
          icon: linkedinIcon,
          link: "https://www.linkedin.com/in/ijeri-omitogun/"
        },
        { icon: githubIcon, link: "https://github.com/ijeriomit" },
        { icon: mediumIcon, link: "https://jeri-omit.medium.com/" }
      ]
    };
  }
};
</script>
<style lang="scss">
@import "@/scss/variables.scss";
@import "@/scss/styles.scss";

$page-height: $header-height + $small-section-height + $section-height +
  $section-height + $large-section-height + $section-height + $footer-height;

#app {
  height: $page-height;
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
  border-top: 5px solid $secondary-color;
}

.content-grid {
  position: relative;
  // top: 60px;
  height: 100%;
  width: 100%;
  display: grid;
  grid-template-columns: 10% 80% 10%;
  grid-template-rows:
    ($small-section-height + $header-height) $section-height $section-height
    $large-section-height
    $section-height $footer-height;
}
html {
  scroll-behavior: smooth;
}
body {
  margin: 0;
  overflow-x: hidden;
  overflow-y: scroll;
}
.background-block {
  z-index: 1;
  height: 100%;
  position: relative;
  grid-column: 1/4;
  box-sizing: border-box;
  display: flex;
  flex-flow: row;
}
.content-block {
  z-index: 2;
  position: relative;
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
  justify-content: center;
  grid-column: 2/2;
  overflow: hidden;
}
.primary-background-block {
  @extend .background-block;
  color: $dark-text-color;
  background-color: $primary-color;
}
.half-background-block {
  @extend .secondary-background-block;
  height: ($section-height / 2);
  border-top: none;
}
.gradient {
  background-image: linear-gradient(
    to right,
    $secondary-color,
    $primary-color,
    $primary-color,
    $primary-color,
    $primary-color,
    $primary-color,
    $primary-color,
    $primary-color,
    $secondary-color
  );
}
.secondary-background-block {
  @extend .background-block;
  background-color: $secondary-color;
  color: $primary-color;
  border-top: #f1f1f1 solid 15px;
  border-left: #f1f1f1 solid 15px;
  border-right: #f1f1f1 solid 15px;
  border-bottom: #f1f1f1 solid 15px;
}
.section-wrapper {
  display: flex;
  flex-flow: column nowrap;
  height: 90%;
  justify-content: space-around;
  overflow: hidden;
}
.section-target {
  align-self: flex-start;
}

@media screen and (max-width: $phone-screen-width) {
  .section-wrapper {
    justify-content: center;
  }
}
body::-webkit-scrollbar {
  display: none;
}
.gear-image {
  width: 30vw;
  height: 30vw;
  align-self: flex-start;
  left: -16vw;
  position: absolute;
}
</style>
