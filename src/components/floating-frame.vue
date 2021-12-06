<template>
  <div class="frame-wrapper">
    <div
      :style="{
        backgroundColor: backgroundColor
      }"
      class="background-layer"
    >
      <img
        :src="imageSrc"
        :style="{
          borderColor: borderColor
        }"
      />
    </div>

    <div ref="frame" class="floating-frame-layer"></div>
  </div>
</template>
<script>
export default {
  name: "floating-frame",
  props: {
    borderColor: {
      type: String,
      required: false,
      default: () => {
        return "red";
      }
    },
    backgroundColor: {
      type: String,
      required: false,
      default: () => {
        return "red";
      }
    },
    horizontalOffset: {
      type: Number,
      required: false,
      default: () => {
        return 1;
      }
    },
    verticalOffset: {
      type: Number,
      required: false,
      default: () => {
        return 1;
      }
    },
    animation: String,
    imageSrc: String
  },
  methods: {
    convertUnit: function(value) {
      return value + "rem";
    }
  },
  mounted: function() {
    let layer = this.$refs["frame"];
    layer.style.marginBottom = this.convertUnit(this.verticalOffset);
    layer.style.marginRight = this.convertUnit(this.horizontalOffset);
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";

.layer {
  height: inherit;
  width: inherit;
  position: absolute;
  border-radius: $box-border-radius;
}
.background-layer {
  @extend .layer;
  background-color: rgb(196, 196, 153);
  z-index: 0;
}

.floating-frame-layer {
  @extend .layer;
  z-index: 1;
  border: black solid 15px;
  box-sizing: border-box;
  height: inherit;
}
.frame-wrapper {
  display: flex;
  flex-flow: row wrap;
  align-items: center;
  justify-content: center;
}
img {
  max-width: 100%;
  max-height: 100%;
  position: absolute;
  bottom: 0px;
  border-width: 0.5px;
}
</style>
