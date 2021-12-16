<template>
  <div class="projects-wrapper">
    <section-title>
      <template v-slot:section-title-content>
        <div class="section-title-operator">(</div>
        <div class="section-title-title">Projects</div>
        <div class="section-title-operator">)</div>
        <div style="width: 15%;" class="section-title-line"></div>
        <div class="section-title-arrow"></div>
        <div class="section-title-operator">{</div>
        <div class="section-title-keyword-1">Projects</div>
        <div class="section-title-operator">}</div>
      </template>
    </section-title>
    <div class="content-section">
      <div class="sections">
        <div
          v-for="(section, index) in projectsSections"
          :key="index"
          @click="selectSection(section)"
          @mouseenter="section.hovered = true"
          @mouseleave="section.hovered = false"
          class="section-label text-box"
          :style="{ 'grid-area': 'section' + (index + 1) }"
          :class="[
            section.hovered && selectedSection != section ? 'fade-85' : '',
            fadeSection(section) ? 'fade-60' : '',
            selectedSection == section ? 'focused-section' : ''
          ]"
        >
          <font-awesome class="icon" :icon="section.icon"></font-awesome>
          <h3 class="section-title">
            {{ section.title }}
          </h3>
        </div>
      </div>
      <div class="projects">
        <project-card
          class="project-card"
          v-for="(project, index) in getSectionProjects(selectedSection)"
          @mouseenter.native="projectHovered(project)"
          @mouseleave.native="project.hovered = false"
          @click.native="selectProject(project)"
          :key="index"
          :projectData="project"
          :fadeImage="!project.hovered"
          :class="[
            project.hovered ? 'focused-project' : '',
            project == selectedProject ? 'selected-project' : ''
          ]"
        ></project-card>
      </div>
    </div>
  </div>
</template>
<script>
import sectionTitle from "@/components/section-title.vue";
import webDevIcon from "@/assets/project-images/section-images/coding-icon-2.png";
import codingIcon from "@/assets/project-images/section-images/coding-icon.jpg";

import BitComponents from "@/assets/project-images/project-images/bit-components-image.png";
import Epoch from "@/assets/project-images/project-images/player-jumping.png";
import Lab from "@/assets/project-images/project-images/LAB.png";
import MasterMind from "@/assets/project-images/project-images/mastermind-image.png";
import ColorPicker from "@/assets/project-images/project-images/color-picker.png";
import ImageManip from "@/assets/project-images/project-images/image-manip.png";
import Ros from "@/assets/project-images/project-images/ROS.png";

import {
  faDesktop,
  faRobot,
  faDatabase
} from "@fortawesome/free-solid-svg-icons";
import { faUnity } from "@fortawesome/free-brands-svg-icons";
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";

import projectCard from "@/components/project-card";

export default {
  name: "projects",
  components: {
    "section-title": sectionTitle,
    "project-card": projectCard,
    "font-awesome": FontAwesomeIcon
  },
  data: function() {
    return {
      selectedSection: null,
      selectedProject: null,
      projectsSections: [
        {
          title: "Front End Development",
          icon: faDesktop,
          hovered: false,
          projects: [
            {
              desc: "",
              title: "Haloguard",
              technologies: ["Vue", "ROS", "Python"],
              links: [""],
              hovered: false
            },
            {
              desc: "",
              title: "Bit Components",
              technologies: ["Vue", "Node"],
              image: BitComponents,
              links: [""],
              hovered: false
            },
            {
              desc: "",
              title: "File Tree",
              technologies: ["Vue", "Node"],
              image: BitComponents,
              links: [""],
              hovered: false
            },
            {
              desc: "",
              title: "Portfolio-Site",
              technologies: ["Vue, Node, Chai, SASS"],
              image: BitComponents,
              links: [""],
              hovered: false
            }
          ]
        },

        {
          title: "Quality Assurance",
          icon: faUnity,
          hovered: false,
          projects: [
            {
              desc: "",
              title: "Epoch",
              technologies: ["Unity3D, C#, Krita, Spriter"],
              image: Epoch,
              links: [""],
              hovered: false
            },
            {
              desc: "",
              title: "Lab",
              technologies: ["Unity3D, C#, Paint3D"],
              image: Lab,
              links: [""],
              hovered: false
            },
            {
              desc: "",
              title: "MasterMind",
              technologies: ["Java, Swing"],
              image: MasterMind,
              links: [""],
              hovered: false
            }
          ]
        },
        {
          title: "Robotics",
          icon: faRobot,
          hovered: false,

          projects: [
            // {
            //   desc: "",
            //   title: "Olympic Arm",
            //   technologies: ["Python", "ROS", "Flexbe"],
            //   image: Ros
            // },
            {
              desc: "",
              title: "ROS-Video-Recorder",
              technologies: ["Python, ROS, PyTest"],
              image: Ros,
              links: [""],
              hovered: false
            }
          ]
        },
        {
          title: "Backend Development",
          icon: faDatabase,
          hovered: false,

          projects: [
            {
              desc: "",
              title: "Image Manipulator",
              technologies: ["Python, OpenCV, PyTest"],
              image: ImageManip,
              links: [""],
              hovered: false
            },
            {
              desc: "",
              title: "Color Picker",
              technologies: ["Python, OpenCV"],
              image: ColorPicker,
              links: [""],
              hovered: false
            },
            {
              desc: "",
              title: "Advent of Code",
              technologies: ["Python", "PyTest"],
              image: codingIcon,
              links: [""],
              hovered: false
            },
            {
              desc: "",
              title: "Rubix-Cube-Solver",
              technologies: ["Python, OpenCV"],
              image: codingIcon,
              links: [""],
              hovered: false
            },
            {
              desc: "",
              title: "SeleniumDemo",
              technologies: ["SeleniumWebDrvier, Python, Vue"],
              image: webDevIcon,
              links: [""],
              hovered: false
            }
          ]
        }
      ]
    };
  },
  methods: {
    selectSection: function(section) {
      console.log("selected section");
      this.selectedSection = section;
      // this.selectProject(section.projects[0]);
    },
    selectProject: function(project) {
      if (this.selectedProject == project) {
        this.selectedProject = null;
      } else {
        this.selectedProject = project;
      }
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
    },
    projectHovered: function(project) {
      if (project != this.selectedProject) {
        project.hovered = true;
      }
    },
    getSectionProjects: function(section) {
      let projects = [];
      if (section != null && "projects" in section) {
        projects = section.projects;
      }
      return projects;
    }
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";
@import "@/scss/styles.scss";

$section-width: 18rem;
$section-height: 13rem;
$offset: 5rem;

$project-height: 15rem;
$project-width: 30rem;

.projects-wrapper {
  width: 90%;
  align-self: center;
  font-family: $vs-code-font;
}
.content-section {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
  align-items: center;
  height: 75%;
}

.sections {
  width: $section-width * 4 + $offset;
  height: $section-height;
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-around;
  align-items: center;
}
.projects {
  width: $project-width * 2 + $offset;
  height: $project-height * 2 + $offset;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
  overflow-y: scroll;
  overflow-x: hidden;
  align-items: flex-start;
  // background-color: $opaque-primary-color;
}
.project-card {
  width: $project-width;
  height: $project-height;
  margin: 10px;
}
.section-label {
  grid-row: 1;
  flex-flow: column nowrap;
  text-align: center;
  width: 18rem;
  font-size: 1.25rem;
  font-weight: bold;
  height: 13rem;
  background-color: $primary-color;
  cursor: pointer;
  grid-area: section;
}
.focused-section {
  width: $section-width + 1rem;
  height: $section-height + 1rem;
}
.selected-project {
  width: 100%;
  height: $section-height * 2;
  order: -1;
}
.focused-project {
  width: $project-width + 1rem;
  height: $project-height + 1rem;
}
</style>
