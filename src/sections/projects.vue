<template>
  <div class="projects-wrapper">
    <section-title
      style="align-self: flex-end;"
      :title="'.projects()'"
      :rightJustified="true"
    ></section-title>
    <div class="content-section">
      <div class="folder">
        <button></button>
        Web Dev
      </div>
      <div class="folder">
        <button></button>
        Unity
      </div>
      <div class="folder">
        <button></button>
        Image and Video Processing
      </div>
      <div class="folder">
        <button></button>
        Other
      </div>
    </div>
  </div>
</template>
<script>
import sectionTitle from "@/components/section-title.vue";

export default {
  name: "projects",
  components: {
    "section-title": sectionTitle
  }
};
</script>
<style lang="scss" scoped>
.projects-wrapper {
  width: 90%;
  height: 100%;
  align-self: center;
}
.content-section {
  // top: 50%;
  // position: relative;
  display: flex;
  flex-flow: row wrap;
  justify-content: space-around;
  align-items: center;
  height: 60%;
}
.folder {
  display: flex;
  flex-flow: column nowrap;
  align-items: center;
  height: 80px;
  justify-content: space-between;
}
button {
  height: 50px;
  width: 50px;
}
</style>
