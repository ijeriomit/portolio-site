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
      <div class="image-section">
        <img class="main-image" />
        <div class="image-reel">
          <button></button>
          <div class="image-square" v-for="photo in photos" :key="photo"></div>
          <button></button>
        </div>
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
      ],
      photos: [1, 2, 3, 4]
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

$image-height: 20rem;
$image-width: 20.5rem;
$image-reel-square-height: $image-width * 0.15;
$image-reel-square-width: $image-width * 0.15;

.work-experience-wrapper {
  width: 97.5%;
}

.options {
  font-size: 25px;
  overflow-y: scroll;
  max-height: 200px;
  border-left: 2px solid $quinary-color;
  list-style-type: none;
  order: 1;
}
.options::-webkit-scrollbar {
  display: none;
}
.main-image {
  width: $image-width;
  height: $image-height;
}
.image-section {
  order: 3;
  margin-left: auto;
  display: flex;
  flex-flow: column nowrap;
  max-width: $image-width;
  height: 25rem;
  align-items: center;
}
.image-reel {
  position: relative;
  top: 20px;
  display: flex;
  width: $image-width;
  flex-flow: row nowrap;
  justify-content: space-around;
}
.image-square {
  height: $image-reel-square-height;
  width: $image-reel-square-width;
  background-color: grey;
}
li > div {
  cursor: pointer;
  display: block;
  padding: 20px 25px;
}
.bullet {
  padding: 10px 0px;
  text-align: left;
}
li > div:hover {
  background-color: $quinary-color;
}
.content-section {
  display: flex;
  flex-flow: row wrap;
  justify-content: flex-start;
  padding-left: 10px;
  color: $dark-text-color;
}
.content-text-section {
  padding-left: 50px;
  padding-right: 50px;
  order: 2;
  text-align: center;
}
</style>
