<template>
  <div class="nav-wrapper">
    <a style="margin-left: 60px" href="#HOME"> Home </a>
    <a href="#ABOUT ME"> About Me</a>
    <a href="#WORK EXPERIENCE"> Work Experience</a>
    <a href="#PROJECTS"> Projects</a>
    <a href="#HOBBIES"> Hobbies</a>
    <a href="#CONTACT ME"> Contact Me</a>
  </div>
</template>
<script>
export default {
  name: "nav-bar"
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";
.nav-wrapper {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
}
a {
  margin-left: 30px;
  padding-left: 20px;
  padding-right: 20px;
  padding-top: 10px;
  padding-bottom: 10px;
  width: fit-content;
  color: $light-text-color;
  text-decoration: none;
}
a:hover {
  background-color: $secondary-color;
  color: $dark-text-color;
}
</style>
