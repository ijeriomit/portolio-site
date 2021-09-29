<template>
  <div id="app">
    <floating-header class="header"></floating-header>
    <div class="content-grid">
      <div class="primary-background-block" style="grid-row: 1/1;"></div>
      <div id="HOME" class="content-block" style="grid-row: 1/1;">
        <home class="section-wrapper" style="padding-bottom: 10vh;"></home>
      </div>
      <div style=" grid-row: 2/2;" class="secondary-background-block">
        <clipart
          v-show="false"
          style="height: 700px; width: 700px;"
          :imageSrc="mattFarImg"
        ></clipart>
      </div>
      <div
        v-show="true"
        id="ABOUT-ME"
        class="content-block"
        style="grid-row: 2/2;"
      >
        <about class="section-wrapper"> </about>
      </div>
      <div
        class="secondary-background-block"
        style="grid-row: 3/3; justify-content: flex-start;"
      >
        <clipart
          v-show="false"
          style="height: 450px; width: 450px "
          class="clip-art"
          :imageSrc="gearsImg"
        ></clipart>
      </div>
      <div
        v-show="true"
        id="WORK-EXPERIENCE"
        class="content-block"
        style="grid-row: 3/3;"
      >
        <workexp class="section-wrapper"></workexp>
      </div>
      <div class="secondary-background-block" style="grid-row: 4/4;">
        <svg
          v-show="false"
          version="1.0"
          xmlns="http://www.w3.org/2000/svg"
          width="225.000000pt"
          height="225.000000pt"
          viewBox="0 0 225.000000 225.000000"
          class="clipart"
          preserveAspectRatio="xMidYMid meet"
        >
          <g
            transform="translate(0.000000,225.000000) scale(0.100000,-0.100000)"
            fill="#008753"
            stroke="none"
          >
            <path
              d="M263 2030 c-46 -11 -115 -54 -140 -87 -53 -73 -53 -68 -53 -818 0
-612 2 -700 16 -742 23 -66 55 -105 116 -139 l53 -29 825 -3 c454 -2 848 0
876 3 78 9 150 57 188 125 l31 55 0 730 0 730 -31 55 c-35 61 -106 113 -171
124 -54 8 -1672 5 -1710 -4z m1135 -142 c7 -7 12 -33 12 -58 0 -25 -5 -51 -12
-58 -7 -7 -36 -12 -65 -12 -59 0 -73 14 -73 70 0 56 14 70 73 70 29 0 58 -5
65 -12z m280 0 c7 -7 12 -33 12 -58 0 -25 -5 -51 -12 -58 -7 -7 -36 -12 -65
-12 -41 0 -54 4 -63 19 -15 29 -12 87 6 105 19 19 104 22 122 4z m280 0 c14
-14 16 -96 3 -116 -5 -9 -26 -12 -67 -10 l-59 3 -3 53 c-2 31 2 60 9 68 14 17
100 19 117 2z m82 -869 l0 -601 -34 -34 -34 -34 -847 0 -847 0 -34 34 -34 34
0 601 0 601 915 0 915 0 0 -601z"
            />
            <path
              d="M604 1194 c-70 -75 -141 -152 -156 -172 -27 -34 -28 -36 -11 -61 9
-14 79 -92 156 -174 96 -101 146 -147 161 -147 26 0 86 58 86 83 0 9 -51 71
-112 137 -62 67 -112 124 -110 128 2 4 53 59 113 124 60 64 109 125 109 135 0
25 -60 83 -87 83 -13 0 -65 -47 -149 -136z"
            />
            <path
              d="M1133 1318 c-14 -18 -145 -613 -141 -640 5 -37 122 -55 132 -20 15
48 136 609 136 629 0 17 -8 24 -37 32 -50 14 -78 14 -90 -1z"
            />
            <path
              d="M1442 1297 c-18 -18 -32 -41 -32 -51 0 -10 49 -70 109 -134 60 -65
110 -121 111 -125 1 -5 -48 -63 -109 -128 -61 -66 -111 -127 -111 -137 0 -25
61 -82 87 -82 14 0 68 50 167 155 80 85 150 163 155 174 13 24 -1 42 -173 225
-88 93 -136 136 -151 136 -11 0 -35 -15 -53 -33z"
            />
          </g>
        </svg>
      </div>
      <div
        v-show="true"
        id="PROJECTS"
        class="content-block"
        style="grid-row: 4/4;"
      >
        <projects class="section-wrapper"></projects>
      </div>
      <div
        class="half-background-block"
        style="grid-row:5/5; align-self: flex-start; background-color: #FFFFFF"
      >
        <img v-show="false" class="clipart" src="@/assets/phone.svg" />
      </div>
      <div
        class="half-background-block"
        style="grid-row:5/5; align-self: flex-end; background-color: #008753; border:none;"
      ></div>
      <div
        v-show="true"
        id="CONTACT-ME"
        class="content-block"
        style="grid-row: 5/5;"
      >
        <contact-me class="section-wrapper"></contact-me>
      </div>
      <div class="footer" style="grid-row: 6/6;"></div>
      <div class="content-block" style="grid-row: 6/6">
        <Footer class="section-wrapper"></Footer>
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
import clipart from "./components/clipart.vue";
import gears from "@/assets/gears.svg";
import mattFar from "@/assets/Mattfarley-background.svg";

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
    clipart: clipart
  },
  data: function() {
    return {
      gearsImg: gears,
      mattFarImg: mattFar
    };
  }
};
</script>
<style lang="scss">
@import "@/scss/variables.scss";

$page-height: $header-height + $small-section-height + $section-height +
  $large-section-height + $section-height + $section-height + $footer-height;

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
    (
      $small-section-height + $header-height
    ) $section-height $large-section-height
    $section-height
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
  // border-top: #f1f1f1 solid 8px;
  // border-bottom: #f1f1f1 solid 4px;
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
  // align-self: end;

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
  border-top: #f1f1f1 solid 30px;
}
.section-wrapper {
  display: flex;
  flex-flow: column nowrap;
  height: 90%;
  justify-content: space-around;
  overflow: hidden;
  // background-color: gray;
}
.clip-art {
  height: 50px;
  width: 50px;
}

@media screen and (max-width: $phone-screen-width) {
  .section-wrapper {
    justify-content: center;
  }
}
body::-webkit-scrollbar {
  // color: blue;
  // border-radius: 15%;
  display: none;
}
</style>
