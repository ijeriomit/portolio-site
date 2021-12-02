<template>
  <div class="nav-wrapper">
    <a
      v-for="(tab, index) in tabs"
      :key="index"
      class="background-label"
      :class="[tab == selectedTab ? 'selected' : '']"
      :aria-label="tab.id.toLowerCase() + '-tab'"
      @click="selectTab(tab)"
      role="tab"
      :href="tab.link"
      >{{ tab.text }}
    </a>
    <!-- <a class="background-label" aria-label="home-tab" role="tab" href="#HOME">
      .home()
    </a>
    <a class="background-label" href="#ABOUT-ME"> .aboutMe()</a>
    <a class="background-label" href="#WORK-EXPERIENCE"> .workExperience()</a>
    <a class="background-label" href="#PROJECTS"> .projects()</a>
    <a class="background-label" href="#CONTACT-ME"> .contactMe()</a> -->
  </div>
</template>
<script>
export default {
  name: "nav-bar",
  props: {
    tabs: {
      type: Array,
      required: true,
      validator: function(tabs) {
        let valid = true;
        console.log("tabs: ", tabs);
        const requiredAttributes = ["link", "text", "id"];
        for (const tab of tabs) {
          if (requiredAttributes.every(attr => attr in tab)) {
            valid = false;
            console.log("invalid prop");
            break;
          }
          console.log("after");
        }
        return valid;
      }
    }
  },
  data: function() {
    return {
      selectedTab: null
    };
  },
  methods: {
    selectTab(tab) {
      this.selectedTab = tab;
    }
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";
@import "@/scss/styles.scss";
.nav-wrapper {
  display: flex;
  flex-direction: row;
  flex-wrap: nowrap;
  font-size: $medium-text-size;
}
a:target {
  margin-top: 5rem;
}
</style>
