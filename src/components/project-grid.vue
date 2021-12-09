<template>
  <div class="grid-wrapper">
    <text-box
      v-for="(section, index) in gridData"
      :key="index"
      v-on:click.native="selectSection(section)"
      @mouseenter.native="section.hovered = true"
      @mouseleave.native="section.hovered = false"
      class="section-label"
      :style="{ 'grid-area': 'section' + (index + 1) }"
      :class="[
        section.hovered && selectedSection != section ? 'fade-60' : '',
        fadeSection(section) ? 'fade-30' : ''
      ]"
    >
      <template v-slot:text-slot>
        <font-awesome class="icon" :icon="section.icon"></font-awesome>
        <h3 class="section-title">
          {{ section.title }}
        </h3>
      </template>
    </text-box>
    <div class="projects">
      <div style="padding: 10px; font-weight: bold">Projects</div>
      <div class="project-list">
        <text-box
          class="project-label center-x-axis"
          v-for="(project, index) in selectedSection.projects"
          :key="index"
          @click.native="selectProject(project)"
        >
          <template v-slot:text-slot>
            <h4 class="section-title">{{ project.title }}</h4>
          </template>
        </text-box>
      </div>
    </div>
    <div class="project-content">
      <h2 class="project-content-title">{{ selectedProject.title }}</h2>

      <img class="project-image" :src="selectedProject.image" />
      <div class="project-text">
        <p class="project-description lorem-ipsum-1"></p>
        <div class="project-links"><button></button> <button></button></div>
        <div class="project-languages">
          <div
            class="project-language"
            v-for="(language, index) in selectedProject.languages"
            :key="index"
          >
            {{ language }}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import textBox from "@/components/text-box.vue";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
// import { library } from "@fortawesome/fontawesome-svg-core";

export default {
  name: "project-grid",
  props: {
    gridData: {
      type: Array
    }
  },
  components: {
    "text-box": textBox,
    "font-awesome": FontAwesomeIcon
  },
  created: function() {
    this.selectedSection = this.gridData[0];
    this.selectedProject = this.selectedSection.projects[0];
    console.log("here");
  },
  data: function() {
    return {
      selectedSection: null,
      selectedProject: null
    };
  },
  methods: {
    selectSection: function(section) {
      console.log("selected section");
      this.selectedSection = section;
      this.selectProject(section.projects[0]);
    },
    selectProject: function(project) {
      this.selectedProject = project;
    },
    fadeSection: function(section) {
      console.log("section faded");
      if (this.selectedSection != null) {
        return section.title != this.selectedSection.title;
      }
      return false;
    },
    sectionHovered: function(section) {
      console.log("hovered: ", section.title);
      section.hovered = true;
    }
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";
@import "@/scss/styles.scss";

.grid-wrapper {
  width: 100%;
  height: 100%;
  display: grid;
  grid-template-columns: 20% 20% 20% 20 20%;
  grid-template-rows: 22.5% 75%;

  grid-template-areas:
    "section1 section2 section3 section4 section5"
    "project-list project-content project-content project-content project-content";
  -moz-column-gap: 5%;
  column-gap: 2.5%;
  row-gap: 3rem;
  align-items: center;
  justify-items: center;
  font-family: $vs-code-font;
}
.section-label {
  grid-row: 1;
  flex-flow: column nowrap;
  text-align: center;
  width: 250px;
  font-size: 1.25rem;
  font-weight: bold;
  height: 200px;
  background-color: $primary-color;
  cursor: pointer;
  grid-area: section;
}
.projects {
  grid-area: project-list;
  width: 100%;
  height: 100%;
}
.project-list {
  height: 90%;
  border-radius: 30px;

  overflow-y: scroll;
  overflow-x: hidden;
}
.project-text {
  align-self: center;
  grid-column: 1/2;
  display: flex;
  flex-flow: column;
}
.project-image {
  max-width: 90%;
  grid-row: 2;
  grid-column: 2/2;
  align-self: center;
}
.project-description {
  grid-row: 2;
}
.project-content {
  grid-area: project-content;
  display: grid;
  grid-template-columns: 48.75% 48.75%;
  grid-template-rows: 10% 90%;
  row-gap: 2.5%;
  column-gap: 2.5%;
  height: 100%;
  width: 100%;
}
.project-content-title {
  justify-self: center;
  align-self: center;
  grid-row: 1;
  grid-column: 1/3;
  margin-block-end: unset;
  margin-block-start: unset;
  font-size: xx-large;
  padding-left: 10px;
  padding-right: 10px;
}

.project-languages {
}
.project-links {
}
.project-label {
  @extend .section-label;
  width: 225px;
  height: 175px;
  background-color: $quinary-color;
  cursor: pointer;
  margin: 5px;
}
</style>
