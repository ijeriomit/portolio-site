<template>
  <div class="section-title">
    <slot name="section-title-content"> </slot>
    <!-- <div class="brackets" style="order: 4;">{</div> -->
  </div>
</template>
<script>
export default {
  name: "section-title"
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";

$horizontal-padding: 1.5rem;
.section-title {
  font-size: $title-text-size;
  align-self: center;
  padding-top: $title-top-offset;
  padding-bottom: $title-bottom-padding;
  font-weight: normal;
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
  width: 100%;
  color: black;
  font-family: Consolas, monaco, monospace;
  justify-content: center;

  .section-title-line {
    background-color: $primary-color;
    height: 6px;
    width: 35%;
    margin-left: 20px;
  }
  .section-title-arrow {
    color: $primary-color;
    align-self: center;
    position: relative;
    bottom: 2px;
    padding-left: $horizontal-padding;
    padding-right: $horizontal-padding;
    &:after {
      content: ">";
    }
  }
  .section-title-keyword-1 {
    color: $quinary-color;
    padding-left: $horizontal-padding;
    padding-right: $horizontal-padding;
  }
  .section-title-keyword-2 {
    color: $quaternary-color;
    padding-left: $horizontal-padding;
    padding-right: $horizontal-padding;
  }
  .section-title-operator {
    color: $quinary-color;
    padding-left: $horizontal-padding;
    padding-right: $horizontal-padding;
  }
  .section-title-title {
    font-weight: bold;
    padding-left: $horizontal-padding;
    padding-right: $horizontal-padding;
  }
}
@media screen and (max-width: $small-screen-width) {
  .section-title {
    font-size: $large-text-size;
  }
}
</style>
