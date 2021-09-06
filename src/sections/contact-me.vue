<template>
  <div class="contact-me-wrapper">
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
export default {
  name: "contact-me"
};
</script>
<style lang="scss" scoped>
@import "@/scss/variables.scss";

.contact-me-wrapper {
  height: 80%;
  border-radius: 25%;
  width: 70%;
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
  font-size: $title-text-size;
  color: $secondary-color;
}
.message {
  height: 200px;
  overflow-y: scroll;
}
</style>
