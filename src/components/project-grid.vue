<template>
  <div class="grid-wrapper">
    <div
      v-for="(section, index) in gridData"
      :key="index"
      @click="selectSection(section)"
      class="section-label"
      :class="[fadeSection(section) ? 'fade' : '']"
    >
      <div class="section-icon"><img :src="section.icon" /></div>
      <h3 class="section-title">{{ section.title }}</h3>
    </div>
    <div v-if="selectedProject != null" class="project-list">
      <div
        class="project-label center-x-axis"
        v-for="(project, index) in selectedSection.projects"
        :key="index"
      >
        <div class="section-icon"><img :src="project.image" /></div>
        <h4 class="section-title">{{ project.title }}}</h4>
      </div>
    </div>
    <div v-if="selectedProject != null" class="project-content">
      <h2 class="project-content-title">{{ selectedProject.title }}</h2>

      <!-- <div class="project-content-section"> -->
      <img class="project-image" :src="selectedProject.image" />
      <div class="project-text-box">
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
export default {
  name: "project-grid",
  props: {
    gridData: {
      type: Array
    }
  },
  data: function() {
    return {
      selectedSection: null,
      selectedProject: null
    };
  },
  methods: {
    makeGridDataObj: function() {},
    selectSection: function(section) {
      this.selectedSection = section;
      this.selectedProject = section.projects[0];
    },
    fadeSection: function(section) {
      if (this.selectedSection != null) {
        return section.title != this.selectedSection.title;
      }
      return false;
    }
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";
@import "@/scss/styles.scss";

.grid-wrapper {
  width: 100%;
  height: 90%;
  display: grid;
  grid-template-columns: 22.5% 22.5% 22.5% 22.5%;
  grid-template-rows: 22.5% 75%;

  grid-template-areas:
    ". . . ."
    "project-list project-content project-content project-content";
  -moz-column-gap: 5%;
  column-gap: 2.5%;
  row-gap: 2.5%;
  align-items: center;
  justify-items: center;
}
.section-label {
  grid-row: 1;
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  text-align: center;
  justify-content: center;
  width: 100%;
  font-size: 1.25rem;
  font-weight: bold;
  height: 100%;
  font-family: $vs-code-font;
  background-color: $primary-color;
  border-radius: 30px;
  cursor: pointer;
}
.section-icon > img {
  max-height: 100%;
  max-width: 100%;
}
.section-icon {
  width: 80px;
}
.project-list {
  grid-area: project-list;
  width: 100%;
  height: 100%;
  border-radius: 30px;

  overflow-y: scroll;
}
.project-image {
  max-width: 90%;
  grid-row: 2;
  grid-column: 2/2;
}
.project-description {
  grid-row: 2;
  grid-column: 1/2;
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
  grid-row: 2;
  grid-column: 1/2;
  justify-self: end;
  align-self: center;
}
.project-links {
  grid-row: 2;
  grid-column: 1/2;
  justify-self: start;
  align-self: center;
}
.project-label {
  @extend .section-label;
  width: 13vw;
  height: 12vw;
  background-color: $quinary-color;
  cursor: pointer;
  margin: 5px;
}
.fade {
  opacity: 30%;
}
</style>
