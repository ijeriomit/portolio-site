<template>
  <div class="title-section" :class="rightJustified ? 'right' : ''">
    <div :class="rightJustified ? 'right' : 'left'">{{ title }}</div>
    <div class="title-line"></div>
  </div>
</template>
<script>
export default {
  name: "section-title",
  props: {
    title: String,
    rightJustified: Boolean
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";

.title-section {
  font-size: $title-text-size;
  align-self: flex-start;
  padding-top: $title-top-offset;
  padding-bottom: $title-bottom-padding;
  font-weight: bold;
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
  width: fit-content;
}
.title-section.right {
  align-self: flex-end;
}
.right {
  order: 2;
}
.left {
  order: 0;
}
.title-line {
  order: 1;
  background-color: $quaternary-color;
  height: 2px;
  width: 400px;
  position: relative;
  margin-left: 20px;
  margin-right: 20px;
}
</style>
