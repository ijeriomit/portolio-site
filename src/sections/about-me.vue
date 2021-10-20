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
        <text-box class="desc-content">
          <template v-slot:text-slot>
            <div class="text">
              Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do
              eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut
              enim ad minim veniam, quis nostrud exercitation ullamco laboris
              nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in
              reprehenderit in voluptate velit esse cillum dolore eu fugiat
              nulla pariatur. Excepteur sint occaecat cupidatat non proident,
              sunt in culpa qui officia deserunt mollit anim id est
              laborum.""Sed ut perspiciatis unde omnis iste natus error sit
              voluptatem accusantium doloremque laudantium, totam rem aperiam,
              eaque ipsa quae ab illo inventore veritatis et quasi architecto
              beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia
              voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur
              magni dolores eos qui ratione voluptatem sequi nesciunt.
            </div>
          </template>
        </text-box>
        <text-box class="skills-content">
          <template class="text" v-slot:text-slot>
            <div>Recent Technologies:</div>
            <div>Javascript</div>
            <div>Python</div>
            <div>Java</div>
            <div>C#</div>
            <div>Vue</div>
            <div>ROS</div>
          </template>
        </text-box>
      </div>
      <layered-frame
        :borderColor="'#4F3E3E'"
        :backgroundColor="'rgb(196, 196, 153)'"
        :horizontalOffset="2.5"
        :verticalOffset="3"
        :imageSrc="image"
        class="image-frame"
      ></layered-frame>
    </div>
  </div>
</template>
<script>
import layeredImageFrame from "@/components/layered-image-frame";
import sectionTitle from "@/components/section-title.vue";
import textBox from "@/components/text-box.vue";

import image from "@/assets/ij-floatin.png";
export default {
  name: "About-Me",
  data: function() {
    return {
      image: image
    };
  },
  components: {
    "layered-frame": layeredImageFrame,
    "section-title": sectionTitle,
    "text-box": textBox
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";

$image-height: 31rem;
$image-width: 25rem;
$phone-image-width: 13rem;
$phone-image-height: 15rem;

.about-me-wrapper {
  width: 97.25%;
  height: 90%;
  margin-top: 3rem;
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
  font-size: $text-size;
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
  font-size: $text-size;
  order: 1;
  // border-radius: 10%;
}
.image-frame {
  order: 2;
  width: $image-width;
  height: $image-height;
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
