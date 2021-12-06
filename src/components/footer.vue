<template>
  <div class="footer-wrapper">
    <div class="socials">
      <a
        :href="iconObj.link"
        target="_blank"
        rel="noopener noreferrer"
        v-for="(iconObj, index) in footerIcons"
        :key="index"
      >
        <font-awesome class="icon" :icon="iconObj.icon"></font-awesome>
        <!-- <img :src="iconObj.icon" /> -->
      </a>
    </div>
    <div class="credit">
      <p>Developed and Designed <b /> by <b /> Ijeri Omitogun</p>
    </div>
  </div>
</template>
<script>
import { FontAwesomeIcon } from "@fortawesome/vue-fontawesome";
import { library } from "@fortawesome/fontawesome-svg-core";

export default {
  components: {
    "font-awesome": FontAwesomeIcon
  },
  created: function() {
    this.footerIcons.map(iconObj => {
      library.add(iconObj);
    });
  },
  props: {
    footerIcons: {
      type: Array
    }
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";

.footer-wrapper {
  flex-flow: row nowrap;
  justify-content: space-between;
  align-items: center;
  height: 100%;
  width: 100%;
}
.socials {
  display: flex;
  margin-right: 2rem;
}
.socials > a:first-child {
  margin-left: 0px;
}
.credit {
  left: 0;
  right: 0;
  margin-left: auto;
  margin-right: auto;
  position: absolute;
  width: fit-content;
}
.icon {
  height: 100%;
  width: 100%;
  color: $tertiary-color;
}
a {
  width: 3rem;
  height: 3rem;
  // background-color: white;
  display: block;
  margin-left: 60px;
}
.footer-wrapper > div {
  text-align: center;
  align-self: center;
}
</style>
