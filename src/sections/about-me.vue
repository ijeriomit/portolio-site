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
        <div class="background-shadow"></div>
        <div class="image-box">
          <img ref="image" src="@/assets/6P8A8200_Original.jpg" />
        </div>
        <div ref="image-shadow" class="titled-image-shadow"></div>
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
  },
  mounted: function() {
    console.log(this.$refs["image"].offsetWidth);
    // this.$refs["image-shadow"].style.width = this.$refs["image"].offsetWidth;
    // this.$refs["image-shadow"].style.height = this.$refs["image"].offsetHeight;
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
  height: 100%;
  margin-top: 3rem;
  // flex-flow: row wrap;
}
.title-section {
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
  height: 90%;
  align-items: flex-start;
  justify-content: space-around;
}
.text-content {
  width: 50%;
  align-self: baseline;
  // padding-top: 10rem;
  max-height: 50%;
  overflow: scroll;
  margin-top: 2.5vw;
  color: $dark-text-color;
  font-size: $text-size;
}
.image-section {
  align-self: flex-start;
  height: $image-height;
  width: $image-width;
  display: flex;
  flex-flow: row wrap;
  align-items: center;
  justify-content: center;
  // background-color: rgb(196, 196, 153);
  background-color: rgb(196, 196, 153);
}
.titled-image-shadow {
  // background-color: $title-color;
  // transform: rotate(7.5deg);
  position: relative;
  bottom: 3rem;
  right: 2.5rem;

  height: 100%;
  width: 100%;
  z-index: 1;
  border: 10px solid $title-color;
  box-shadow: 30px 15px 20px rgba(25, 25, 25, 0.1);
}
.image-box {
  max-height: $image-height;
  max-width: $image-width;
  // border: 0.1px solid $quinary-color;
  box-shadow: 10px 15px 20px rgba(25, 25, 25, 0.1);
  margin-bottom: 3rem;
  margin-right: 2.5rem;
  position: absolute;
  z-index: 1;
}
.background-shadow {
  z-index: -1;
  height: $image-height + 6rem;
  width: $image-width + 6rem;
  margin-right: 2.5rem;
  margin-bottom: 2.5rem;
  // background-color: aliceblue;
  background-image: radial-gradient(#9fb5ccf8, #ffffff);
  position: absolute;
}
img {
  // right: 0.5rem;
  // top: 1.5rem;
  position: relative;
  max-width: 100%;
  max-height: 100%;
}

@media screen and (max-width: $small-screen-width) {
  .content-section {
    flex-flow: column nowrap;
    // align-items: center;
    justify-content: space-;
  }
  .text-content {
    width: 100%;
    word-break: break-word;
    text-align: center;
    margin-top: 0;
    font-size: $phone-text-size;
    max-height: 30%;
  }
  .image-section {
    align-self: center;
    width: $phone-image-width + 1rem;
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
