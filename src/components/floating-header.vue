<template>
  <div class="wrapper">
    <div class="title-section">
      <div class="logo">
        <img style="height: 100%; width: 100%;" :src="logo" />
      </div>
      <div class="title">
        IJERI OMITOGUN
      </div>
    </div>
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
.wrapper {
  width: 100%;
  background-color: $primary-color;
  // opacity: 67%;
  display: flex;
  flex-flow: column nowrap;
  position: fixed;
}
.title-section {
  display: flex;
  flex-flow: row nowrap;
  justify-content: flex-start;
  align-items: center;
  order: 1;
}
.nav-section {
  // display: flex;
  // flex-flow: row nowrap;
  order: 2;
  border-bottom: 2px solid $primary-color;
}
.logo {
  width: 40px;
  height: 40px;
  order: 1;
  padding: 5px;
}
.title {
  order: 2;
  font-family: $font;
  font-size: large;
  color: $light-text-color;
  align-self: baseline;
  padding: 5px;
}
</style>
