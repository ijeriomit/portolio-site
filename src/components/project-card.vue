<template>
  <div class="card-wrapper">
    <img :src="projectData.image" :class="[fadeImage ? 'fade-60' : '']" />
    <div class="text-content">
      <div class="title">{{ projectData.title }}</div>
      <div class="description">{{ projectData.desc }}</div>
      <div class="technologies">
        <span>{{ projectData.tech }}</span>
      </div>
      <a class="links">{{ projectData.link }} </a>
    </div>
  </div>
</template>
<script>
export default {
  name: "project-card",
  props: {
    projectData: Object,
    fadeImage: { type: Boolean, default: true }
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";
@import "@/scss/styles.scss";

.card-wrapper {
  border-radius: $box-border-radius/2;
  background-color: $quinary-color;
  box-shadow: 0 15px 20px rgba(25, 25, 25, 0.1);
  transition: 0.9s ease;
  width: 15rem;
  height: 25rem;
  overflow: hidden;
  cursor: pointer;
}
</style>
