<template>
  <div class="footer-wrapper">
    <a class="social-icon"><i></i></a>
    <a class="social-icon"><i></i></a>
    <a class="social-icon"><i></i></a>
    <div>
      <p>Developed and Designed <b /> by <b /> Ijeri Omitogun</p>
    </div>
  </div>
</template>
<script>
export default {};
</script>
<style lang="scss" scoped>
.footer-wrapper {
  flex-flow: row nowrap;
  justify-content: flex-start;
  align-items: center;
  height: 100%;
  width: 100%;
}
a {
  width: 50px;
  height: 50px;
  background-color: white;
  display: block;
  margin-left: 60px;
}
.footer-wrapper > div {
  text-align: center;
  align-self: center;
}
</style>
