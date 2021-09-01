<template>
  <div class="work-experience-wrapper">
    <section-title :title="'.workExperience()'"></section-title>
    <div class="content-section">
      <ul class="options">
        <li v-for="company in companies" :key="company">
          <div @click="loadJob('HMI')">
            {{ company }}
          </div>
        </li>
      </ul>
      <div class="content-text-section">
        <div class="text-section-title">
          <h2>Job Title</h2>
          <h3>Start date — End Date</h3>
        </div>
        <ul class="description-bullet-points">
          <li class="bullet" v-for="bullet in bulletPoints" :key="bullet">
            {{ bullet }}
          </li>
        </ul>
      </div>
      <div class="image-reel">
        <button></button>
        <img style="height: 475px; width: 450px;" />
        <button></button>
      </div>
    </div>
    <div class="highlight-reel"></div>
  </div>
</template>
<script>
import sectionTitle from "@/components/section-title.vue";

export default {
  name: "work-experience",
  components: {
    "section-title": sectionTitle
  },
  data: function() {
    return {
      experience: "",
      companies: ["Houston Mechatronics", "Apple", "Hulu", "spotify", "apple"],
      bulletPoints: [
        "aid odda dadfda ida jai odjf",
        "oiadioahif a jdfio ajdfadoifaj oidfja",
        "oiajdfioad adjoiadfjai adodjfioadf ioajdf"
      ]
    };
  },
  methods: {
    loadJob() {},
    loadJobPhotos() {},
    loadJobDescription() {}
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";

.work-experience-wrapper {
  display: flex;
  flex-flow: column nowrap;
  align-items: flex-start;
  position: relative;
  left: 10vw;
  width: 65%;
}

.options {
  font-size: 25px;
  overflow-y: scroll;
  max-height: 200px;
  border-left: 3px solid $quinary-color;
  list-style-type: none;
}
.options::-webkit-scrollbar {
  display: none;
}
.image-reel {
  margin-left: auto;
  display: flex;
  flex-flow: row nowrap;
  align-items: center;
}
li > div {
  cursor: pointer;
  display: block;
  padding: 20px 25px;
}
.bullet {
  padding: 10px 0px;
}
li > div:hover {
  background-color: $quinary-color;
}
.content-section {
  display: flex;
  flex-flow: row nowrap;
  justify-content: flex-start;
  width: 100%;
  padding-left: 100px;
  color: $dark-text-color;

  //   cursor: pointer;
}
.content-text-section {
  padding-left: 50px;
  padding-right: 50px;
}
// .content-section:hover {
//   color: red;
// }
</style>
