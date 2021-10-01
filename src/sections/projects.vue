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
        Web Dev
      </div>
      <div class="folder">
        <clipart class="button" :imageSrc="unityImg"></clipart>
        Game Dev
      </div>
      <div class="folder">
        <clipart class="button" :imageSrc="imageProcessingImg"></clipart>
        Image and Video Processing
      </div>
      <div class="folder">
        <clipart class="button" :imageSrc="codingImg"></clipart>
        Python
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
  height: 80px;
  justify-content: space-between;
}
.button {
  width: 80px;
}
</style>
