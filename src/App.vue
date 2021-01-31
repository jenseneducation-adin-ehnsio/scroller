<template>
  <div class="progress_bar"></div>
  <div @click="animate" :class="{ bigger: cubeAnimate }" class="cube-wrap">
    <div class="cube">
      <div class="side top"><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6></div>
      <div class="side bottom"><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6></div>
      <div class="side front"><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6></div>
      <div class="side back"><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6></div>
      <div class="side left"><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6></div>
      <div class="side right"><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6><h6>afonso</h6></div>
    </div>
  </div>
  <router-view />
</template>



<script>

export default {
  name: "App",

  data() {
    return {
      cubeAnimate: false
    }
  },

  created() {
    document.body.style.setProperty('--scroll', 0);
    window.addEventListener('scroll', () => {
      document.body.style.setProperty('--scroll',window.pageYOffset / (document.body.offsetHeight - window.innerHeight));
    }, false);
  },

  methods: {
    animate() {
      this.cubeAnimate = true
      setTimeout(() => {
        this.cubeAnimate = false
      }, 500);
    }
  },

};
</script>

<style lang="scss">
@import "@/styles/index";

</style>
