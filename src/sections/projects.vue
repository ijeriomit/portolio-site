<template>
  <div class="projects-wrapper">
    <section-title
      :title="'.projects()'"
      :rightJustified="true"
    ></section-title>
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
  display: flex;
  flex-flow: column nowrap;
  //   justify-content: flex-end;
  width: 65vw;
  //   max-width: 1vw;
  //   align-self: flex-end;
  //   justify-self: flex-end;
  margin-left: 0;
}
</style>
