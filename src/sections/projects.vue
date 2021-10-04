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
      <div class="folder">
        <clipart class="button" :imageSrc="webDevImg"></clipart>
        <div>Web Dev</div>
      </div>
      <div class="folder">
        <clipart class="button" :imageSrc="unityImg"></clipart>
        <div>Game Dev</div>
      </div>
      <div class="folder">
        <clipart class="button" :imageSrc="imageProcessingImg"></clipart>
        <div>Image and Video Processing</div>
      </div>
      <div class="folder">
        <clipart class="button" :imageSrc="codingImg"></clipart>
        <div>Python</div>
      </div>
    </div>
  </div>
</template>
<script>
import sectionTitle from "@/components/section-title.vue";
import clipart from "../components/clipart.vue";
import imageProcessingIcon from "@/assets/vision-logo.png";
import unityIcon from "@/assets/unity.png";
import webDevIcon from "@/assets/coding-icon-2.png";
import codingIcon from "@/assets/coding-icon.jpg";

export default {
  name: "projects",
  data: function() {
    return {
      unityImg: unityIcon,
      codingImg: codingIcon,
      webDevImg: webDevIcon,
      imageProcessingImg: imageProcessingIcon
    };
  },
  components: {
    "section-title": sectionTitle,
    clipart: clipart
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
