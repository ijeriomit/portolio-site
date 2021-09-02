<template>
  <div class="home-wrapper">
    <span class="first-line">Hi, my name is,</span>
    <span class="second-line">Ijeri Omitogun </span>
    <span class="third-line">
      Software Engineer with Robotics Experience and a Passion For Web
      Development
    </span>
  </div>
</template>
<script>
export default {
  name: "home"
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";
.home-wrapper {
  width: 80%;
}

.line {
  font-size: x-large;
  font-weight: bold;
  padding-bottom: 25px;
  padding-top: 25px;
}
.first-line {
  @extend .line;
  order: 1;
  color: $secondary-color;
  font-size: 35px;
}
.second-line {
  @extend .line;
  order: 2;
  color: $dark-text-color;
  font-size: 50px;
}
.third-line {
  @extend .line;
  order: 3;
  color: $title-color;
  font-size: 45px;
}
</style>
