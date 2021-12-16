<template>
  <div class="about-me-wrapper">
    <section-title>
      <template v-slot:section-title-content>
        <div class="section-title-title">AboutMe:</div>
        <div class="section-title-keyword-1">function()</div>
        <div class="section-title-line"></div>
        <div class="section-title-arrow"></div>
      </template>
    </section-title>
    <div class="content-section">
      <div class="text-boxes">
        <div class="desc-content text-box">
          <div class="text lorem-ipsum-1"></div>
        </div>
        <div class="skills-content text-box">
          <span>Recent Technologies:</span>
          <ul class="technologies">
            <li v-for="(item, index) in technologies" :key="index">
              {{ item }}
            </li>
          </ul>
        </div>
      </div>
      <floating-frame
        :borderColor="'#4F3E3E'"
        :backgroundColor="'rgb(196, 196, 153)'"
        :horizontalOffset="3"
        :verticalOffset="3"
        :imageSrc="image"
        class="image-frame"
      ></floating-frame>
    </div>
  </div>
</template>
<script>
import FloatingFrame from "@/components/floating-frame";
import sectionTitle from "@/components/section-title.vue";

import image from "@/assets/about-me-images/ij-floatin.png";
export default {
  name: "About-Me",
  data: function() {
    return {
      image: image,
      aboutMeText: "",
      technologies: ["Javascript", "Python", "Vue", "Angular", "Node.js", "ROS"]
    };
  },
  components: {
    "floating-frame": FloatingFrame,
    "section-title": sectionTitle
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";
@import "@/scss/styles.scss";

$image-height: 31rem;
$image-width: 25rem;
$phone-image-width: 13rem;
$phone-image-height: 15rem;

.about-me-wrapper {
  width: 97.25%;
  height: 90%;
  margin-top: 3rem;
  font-family: $vs-code-font;
}
.technologies {
  display: grid;
  grid-template-columns: 50% 50%;
  grid-template-rows: 33.33% 33.33% 33.33%;
  width: 90%;
  height: 90%;
  gap: 0 10px;
  li {
    padding: 5px;
  }
}
.content-section {
  display: flex;
  flex-flow: row wrap;
  height: 85%;
  align-items: flex-start;
  justify-content: space-around;
}
.desc-content {
  width: 30rem;
  height: 30rem;
  color: $dark-text-color;
  background-color: $primary-color;
  order: 0;
}
.text-boxes {
  display: flex;
  flex-flow: row wrap;
  width: 65%;
  justify-content: space-around;
}
.skills-content {
  width: 20rem;
  height: 12.5rem;
  color: $dark-text-color;
  order: 1;
  display: flex;
  flex-flow: column;
}
.image-frame {
  order: 2;
  width: $image-width;
  height: $image-height;
}
.text {
  width: 90%;
  height: 90%;
  overflow: hidden;
}
@media screen and (max-width: $small-screen-width) {
  .content-section {
    flex-flow: column nowrap;
    justify-content: space-evenly;
  }
  .text-content {
    width: 100%;
    max-height: 45%;
    overflow: scroll;
    word-break: break-word;
    text-align: center;
    margin-top: 0;
    font-size: $phone-text-size;
    order: 1;
  }
  .image-frame {
    align-self: center;
    width: $phone-image-width + 1rem;
    order: 0;
    height: $phone-image-height + 1rem;
  }
  .image-box {
    width: 100%;
    height: 100%;
  }
}
@media screen and (max-width: $phone-screen-width) {
}
</style>
