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
      <project-grid :gridData="projectsSections"></project-grid>
    </div>
  </div>
</template>
<script>
import sectionTitle from "@/components/section-title.vue";
import imageProcessingIcon from "@/assets/vision-logo.png";
import unityIcon from "@/assets/unity.png";
import webDevIcon from "@/assets/coding-icon-2.png";
import codingIcon from "@/assets/coding-icon.jpg";
import projectGrid from "@/components/project-grid";
import ProjectGrid from "../components/project-grid.vue";

export default {
  name: "projects",
  data: function() {
    return {
      unityImg: unityIcon,
      codingImg: codingIcon,
      webDevImg: webDevIcon,
      imageProcessingImg: imageProcessingIcon,
      projectsSections: [
        {
          title: "Web Dev",
          icon: webDevIcon,
          projects: [
            {
              desc: "",
              title: "project1",
              languages: ["Python, ROS"],
              image: webDevIcon
            },
            {
              desc: "",
              title: "project2",
              languages: ["Python, ROS"],
              image: webDevIcon
            },
            {
              desc: "",
              title: "project3",
              languages: ["Python, ROS"],
              image: webDevIcon
            },
            {
              desc: "",
              title: "project4",
              languages: ["Python, ROS"],
              image: webDevIcon
            },
            {
              desc: "",
              title: "project5",
              languages: ["Python, ROS"],
              image: webDevIcon
            },
            {
              desc: "",
              title: "project3",
              languages: ["Python, ROS"],
              image: imageProcessingIcon
            }
          ]
        },
        {
          title: "Game Dev",
          icon: unityIcon,
          projects: [
            {
              desc: "",
              title: "project1",
              languages: ["Python, ROS"],
              image: unityIcon
            },
            {
              desc: "",
              title: "project2",
              languages: ["Python, ROS"],
              image: unityIcon
            },
            {
              desc: "",
              title: "project3",
              languages: ["Python, ROS"],
              image: unityIcon
            }
          ]
        },
        {
          title: "Image/Video ProcessinG",
          icon: imageProcessingIcon,
          projects: [
            {
              desc: "",
              title: "project1",
              languages: ["Python, ROS"],
              image: imageProcessingIcon
            },
            {
              desc: "",
              title: "project2",
              languages: ["Python, ROS"],
              image: imageProcessingIcon
            },
            {
              desc: "",
              title: "project3",
              languages: ["Python, ROS"],
              image: imageProcessingIcon
            }
          ]
        },
        {
          title: "Python",
          icon: codingIcon,
          projects: [
            {
              desc: "",
              title: "project1",
              languages: ["Python, ROS"],
              image: codingIcon
            },
            {
              desc: "",
              title: "project2",
              languages: ["Python, ROS"],
              image: codingIcon
            },
            {
              desc: "",
              title: "project3",
              languages: ["Python, ROS"],
              image: webDevIcon
            }
          ]
        }
      ]
    };
  },
  components: {
    "section-title": sectionTitle,
    "project-grid": projectGrid,
    ProjectGrid
  }
};
</script>
<style lang="scss" scoped>
.projects-wrapper {
  width: 90%;
  align-self: center;
}
.content-section {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
  align-items: center;
  height: 60%;
}
.folder {
  display: flex;
  display: none;
  flex-flow: column nowrap;
  align-items: center;
  text-align: center;
  justify-content: center;
  width: 300px;
  font-size: 1.25rem;
  font-weight: bold;
  height: 200px;
  font-family: Consolas, monaco, monospace;
  background-color: #008753cf;
  border-radius: 30px;
}
.button {
  width: 80px;
}
</style>
