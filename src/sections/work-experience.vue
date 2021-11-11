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
    <text-box class="content-section">
      <template v-slot:text-slot>
        <div class="text-section">
          <ul class="experiences-list">
            <li
              v-for="experience in experiences"
              :key="experience"
              @click="selectExperience(experience)"
            >
              <div>
                {{ experience.company }}
              </div>
            </li>
          </ul>
          <div class="experience-text-section">
            <div class="text-section-title">
              <h2>{{ selectedExperience.jobTitle }}</h2>
              <h3>
                {{ selectedExperience.startDate }} —
                {{ selectedExperience.endDate }}
              </h3>
            </div>
            <ul class="description-bullet-points">
              <li
                class="bullet"
                v-for="task in selectedExperience.tasks"
                :key="task"
              >
                {{ task }}
              </li>
            </ul>
          </div>
        </div>
        <img class="image-section" :src="selectedExperience.logo" />
        <!-- <image-carousel
          class="image-section"
          :slides="selectedExperience.images"
          :descriptions="[1, 2, 3]"
          :photoHeight="20"
          :photoWidth="20"
          :sizeType="'rem'"
        ></image-carousel> -->
      </template>
    </text-box>
  </div>
</template>
<script>
// import imageCarousel from "@/components/image-carousel.vue";
import image1 from "@/assets/work-experience-images/HMI.png";
import sectionTitle from "@/components/section-title.vue";
import textBox from "@/components/text-box.vue";

export default {
  name: "work-experience",
  components: {
    // "image-carousel": imageCarousel,
    "section-title": sectionTitle,
    "text-box": textBox
  },
  mounted: function() {
    this.selectedExperience = this.experiences[0];
  },
  data: function() {
    return {
      experiences: [
        {
          company: "Houston Mechatronics",
          tasks: [
            "aid odda dadfda ida jai odjf",
            "oiadioahif a jdfio ajdfadoifaj oidfja",
            "oiajdfioad adjoiadfjai adodjfioadf ioajdf"
          ],
          jobTitle: "Software Engineer",
          startDate: "04/2019",
          endDate: "06/2021",
          logo: image1
        },
        {
          company: "Google",
          tasks: [
            "oiadioahif a jdfio ajdfadoifaj oidfja",
            "aid odda dadfda ida jai odjf",
            "oiajdfioad adjoiadfjai adodjfioadf ioajdf"
          ],
          jobTitle: "Front End Developer",
          startDate: "11/2021",
          endDate: "Current",
          logo: image1
        },
        {
          company: "Apple",
          tasks: [
            "oiajdfioad adjoiadfjai adodjfioadf ioajdf",
            "aid odda dadfda ida jai odjf",
            "oiadioahif a jdfio ajdfadoifaj oidfja"
          ],
          jobTitle: "Software Engineer",
          startDate: "04/2019",
          endDate: "06/2021",
          logo: image1
        }
      ],
      selectedExperience: null
    };
  },
  methods: {
    selectExperience: function(exp) {
      this.selectedExperience = exp;
    }
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
  font-family: $vs-code-font;
}

.experiences-list {
  font-size: 25px;
  overflow-y: scroll;
  max-height: 200px;
  border-left: 2px solid $quinary-color;
  list-style-type: none;
  order: 1;
}
.experiences-list::-webkit-scrollbar {
  display: none;
}

.image-section {
  order: 3;
  padding-left: 25px;
  // height: 20rem;
  max-width: 20rem;
  overflow: hidden;
  padding-right: 25px;
}
.selected-company {
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
  color: $light-text-color;
  background-color: $tertiary-color;
}
.experience-text-section {
  padding-left: 15px;
  padding-right: 50px;
  order: 2;
  text-align: center;
}
</style>
