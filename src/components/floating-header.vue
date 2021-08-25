<template>
  <div class="header-wrapper">
    <div class="title-section">
      <a class="logo" href="#HOME">
        <img style="height: 100%; width: 100%;" :src="logo" />
      </a>
      <div class="title">
        IJERI OMITOGUN
      </div>
    </div>
    <!-- <div class="divider"></div> -->
    <div class="nav-section">
      <nav-bar />
    </div>
  </div>
</template>
<script>
import NavBar from "@/components/nav-bar.vue";
import logo from "@/assets/logo.png";
export default {
  name: "floating-header",
  components: {
    "nav-bar": NavBar
  },
  data: function() {
    return {
      logo: logo
    };
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";
.header-wrapper {
  width: 100%;
  top: 0;
  left: 0;
  background-color: $primary-color;
  // opacity: 67%;
  display: flex;
  flex-flow: row nowrap;
  flex-grow: 0;
  position: fixed;
  align-items: center;
  padding-top: 15px;
  padding-bottom: 15px;
  border-bottom: rgb(59, 168, 92) solid 1.5px;
  justify-content: space-around;
}
.title-section {
  display: flex;
  flex-flow: row nowrap;
  justify-content: flex-start;
  order: 1;
  right: 5%;
  position: relative;
}
.nav-section {
  order: 2;
  left: 5%;
  position: relative;
  border-bottom: 2px solid $primary-color;
}
// .divider {
//   background-color: white;
//   height: 5px;
//   order: 2;
//   width: 100%;
// }
.logo {
  width: 40px;
  height: 40px;
  order: 1;
  // padding: 5px;
  padding-left: 20px;
  padding-right: 20px;
  // align-self: center;
}
.title {
  order: 2;
  font-family: $font;
  font-size: xx-large;
  color: $light-text-color;
  align-self: baseline;
  font-weight: bold;
  // padding: 5px;
}
</style>
