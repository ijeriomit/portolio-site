<template>
  <div class="about-me-wrapper">
    <section-title :title="'.aboutMe()'"></section-title>
    <div class="content-section">
      <div class="text-content">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim
        veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
        commodo consequat. Duis aute irure dolor in reprehenderit in voluptate
        velit esse cillum dolore
      </div>
      <div>
        <div class="image-box">
          <img />
        </div>
        <div class="titled-image-shadow"></div>
      </div>
    </div>
  </div>
</template>
<script>
import sectionTitle from "@/components/section-title.vue";
export default {
  name: "About-Me",
  components: {
    "section-title": sectionTitle
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";

.about-me-wrapper {
  display: flex;
  font-size: $text-size;
  flex-flow: column nowrap;
  justify-content: space-around;
  height: 100%;
  width: 50%;
}
.title-section {
  font-size: $title-text-size;
  align-self: flex-start;
  padding-top: $title-top-padding;
  padding-bottom: $title-bottom-padding;
  font-weight: bold;
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
}
.title-line {
  background-color: $dark-text-color;
  height: 2px;
  width: 400px;
  position: relative;
  left: 20px;
}
.content-section {
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-between;
  align-items: center;
  padding-bottom: 15vh;
  // padding-right: 5vw;
  // padding-left: 5vw;
}
.text-content {
  width: 700px;
  align-self: flex-start;
  padding-top: 10px;
  color: $dark-text-color;
}
.titled-image-shadow {
  background-color: $title-color;
  transform: rotate(80deg);
  height: 475px;
  width: 450px;
  z-index: -2;
}
.image-box {
  height: 475px;
  width: 450px;
  background-color: rgb(196, 196, 153);
  position: absolute;
  z-index: 1;
}
</style>
