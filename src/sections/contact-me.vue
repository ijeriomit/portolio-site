<template>
  <div class="contact-me-wrapper">
    <section-title>
      <template v-slot:section-title-content>
        <div class="section-title-keyword-1">function()</div>
        <div class="section-title-operator">{</div>
        <div class="section-title-keyword-2">return</div>
        <div class="section-title-title">WorkExperience</div>
        <div class="section-title-operator">}</div>
      </template>
    </section-title>
    <div class="title">Contact Me</div>
    <form>
      <div>Reason For Reaching Out</div>
      <select />
      <div>Subject Line</div>
      <input />
      <div>Message</div>
      <input class="message" />
    </form>
  </div>
</template>
<script>
import sectionTitle from "@/components/section-title.vue";

export default {
  name: "contact-me",
  components: {
    "section-title": sectionTitle
  }
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";

.contact-me-wrapper {
  height: 80%;
  border-radius: 25%;
  width: 85%;
  align-self: center;
  align-items: center;
  justify-content: center;
  background-color: $tertiary-color;
  color: $secondary-color;
  font-size: $text-size;
}
form {
  display: flex;
  flex-flow: column nowrap;
  justify-content: space-around;
  height: 50%;
  width: 85%;
}
.title {
  font-size: 3.5rem;
  color: $secondary-color;
}
.message {
  height: 200px;
  overflow-y: scroll;
}
</style>
