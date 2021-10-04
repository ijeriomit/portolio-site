<template>
  <div class="grid-wrapper">
    <div v-for="header in gridData.headers" :key="header" class="header-label">
      <div class="header-icon"><img :src="header.icon" /></div>
      <h3 class="header-title">{{ header.title }}</h3>
    </div>
    <div v-if="selectedSection != null" class="project-list">
      <div v-for="project in selectedSection.projects" :key="project"></div>
    </div>
    <div v-if="selectedSection != null" class="project-content">
      <div class="project-image-section">
        <div class="project title"></div>
        <img class="project-image" :src="selectedProject.image" />
      </div>
      <div class="project-content-description-section">
        <p class="project-description"></p>
        <div class="project-lanuages">
          <div
            class="project-language"
            v-for="language in selectedProject.lanuages"
            :key="language"
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
    gridHeaderLabels: {
      type: Array,
      required: true,
      validator: function() {}
    },
    gridProjects: {
      type: [Array],
      required: true,
      validator: function() {}
    }
  },
  data: function() {
    return {
      gridData: {},
      selectedSection: null,
      selectedProject: null
    };
  },
  methods: {
    makeGridDataObj: function() {},
    selectSection: function(headerSection) {
      this.selectedSection = headerSection;
      this.selectedProject = headerSection.projects[0];
    }
  },
  created: function() {
    this.gridData = this.makeGridDataObj();
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";

.grid-wrapper {
  width: 100%;
  height: 85%;
  display: grid;
  grid-template-columns: 20% 20% 20% 20%;
  grid-template-rows: 20% 75%;
  grid-template-areas:
    " . . . ."
    "project-list project-content project-content project-content project-content";
  column-gap: 5%;
  row-gap: 5%;
  align-items: center;
  justify-items: center;
}
.header-label {
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
}
.header-icon > img {
  max-height: 100%;
  max-width: 100%;
}
.header-icon {
  width: 80px;
}
.project-list {
  grid-area: "project-list";
  background-color: $tertiary-color;
  border-radius: 30px;
}
</style>
