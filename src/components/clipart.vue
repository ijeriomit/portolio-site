<template>
  <div class="clipart-bg">
    <img :src="imageSrc" class="clipart" />
  </div>
</template>

<script>
export default {
  name: "clipart",
  props: {
    imageSrc: String
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";

.clipart-bg {
  // border-radius: 100%;
  // background-color: rgba($color: #000000, $alpha: 0.9);
  //   opacity: 70%;
}
.clipart {
  height: 100%;
  max-width: 100%;
  position: relative;
  padding-left: 5px;
  padding-right: 5px;
  //   opacity: 100%;
}
</style>
