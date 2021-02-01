<template>
  <div class="progress_bar"></div>
  <div class="cube-wrap">
    <div class="cube">
      <div class="side top"><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6></div>
      <div class="side bottom"><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6></div>
      <div class="side front"><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6></div>
      <div class="side back"><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6></div>
      <div class="side left"><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6></div>
      <div class="side right"><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6><h6>wazaaa</h6></div>
    </div>
  </div>
  <router-view />
</template>



<script>

export default {
  name: "App",

  created() {
    document.body.style.setProperty('--scroll', 0);
    window.addEventListener('scroll', () => {
      document.body.style.setProperty('--scroll',window.pageYOffset / (document.body.offsetHeight - window.innerHeight));
    }, false);
  },



};
</script>

<style lang="scss">
@import "@/styles/index";

</style>
