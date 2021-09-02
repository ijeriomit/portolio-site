<template>
  <div class="about-me-wrapper">
    <section-title :title="'.aboutMe()'"></section-title>
    <div class="content-section">
      <div class="text-content">
        Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod
        tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim
        veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea
        commodo consequat. Duis aute irure dolor in reprehenderit in voluptate
        velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint
        occaecat cupidatat non proident, sunt in culpa qui officia deserunt
        mollit anim id est laborum.""Sed ut perspiciatis unde omnis iste natus
        error sit voluptatem accusantium doloremque laudantium, totam rem
        aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto
        beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia
        voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni
        dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam
        est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit,
        sed quia non numquam eius modi tempora incidunt ut labore et dolore
        magnam aliquam quaerat voluptatem. Ut enim ad minima veniam,
      </div>
      <div class="image-section">
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

$image-height: 20rem;
$image-width: 20.5rem;

.about-me-wrapper {
  font-size: $text-size;
  width: 90%;
}
.title-section {
  font-size: $title-text-size;
  align-self: flex-start;
  position: relative;
  top: $title-top-offset;
  padding-bottom: $title-bottom-padding;
  font-weight: bold;
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
}
.content-section {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
  align-items: center;
  top: $title-top-offset;
  position: relative;
  flex-shrink: 2;
}
.text-content {
  width: 700px;
  flex-flow: column;
  align-self: flex-start;
  padding-top: 10px;
  padding-bottom: 7.5vh;
  color: $dark-text-color;
}
.image-section {
  align-self: baseline;
}
.titled-image-shadow {
  background-color: $title-color;
  transform: rotate(80deg);
  height: $image-height;
  width: $image-width;
  z-index: -2;
}
.image-box {
  height: $image-height;
  width: $image-width;
  background-color: rgb(196, 196, 153);
  position: absolute;
  z-index: 1;
  flex: 1 2 auto;
}
</style>
