<template>
  <div class="work-experience-wrapper">
    <section-title style="width: 90%;">
      <template v-slot:section-title-content>
        <div class="section-title-keyword-1">function()</div>
        <div class="section-title-operator">{</div>
        <div class="section-title-keyword-2">return</div>
        <div class="section-title-title">WorkExperience</div>
        <div class="section-title-operator">}</div>
      </template>
    </section-title>
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
      <image-carousel
        class="image-section"
        :slides="photos"
        :descriptions="[1, 2, 3]"
      ></image-carousel>
    </div>
  </div>
</template>
<script>
import imageCarousel from "@/components/image-carousel.vue";
import image1 from "@/assets/avatar-background.svg";
import image2 from "@/assets/IMG_9687_SparkVideo.gif";
import image3 from "@/assets/6P8A8272_Original.jpg";
import sectionTitle from "@/components/section-title.vue";

export default {
  name: "work-experience",
  components: {
    "image-carousel": imageCarousel,
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
      photos: [image1, image2, image3]
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
  height: 90%;
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

.image-section {
  order: 3;
  padding-left: 25px;

  padding-right: 25px;
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
  justify-content: center;
  color: $dark-text-color;
}
.content-text-section {
  padding-left: 15px;
  padding-right: 50px;
  order: 2;
  text-align: center;
}
</style>
