<template>
  <div class="header-wrapper">
    <div class="title-section">
      <a class="logo" href="#HOME">
        <img style="height: 100%; width: 100%;" :src="logo" />
      </a>
      <div class="title">
        .IO
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
.header-wrapper {
  width: 100%;
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
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

.logo {
  width: 50px;
  height: 50px;
  order: 1;
  padding-left: 20px;
  padding-right: 20px;
  align-self: center;
}
.title {
  order: 2;
  font-family: $font;
  color: $light-text-color;
  align-self: center;
  font-weight: bold;
  font-size: xxx-large;
}
</style>
