<template>
  <main class="home">
    <header >
      <h1 class="first" :class="{ fade: visible.first }">AFONSO</h1>
    </header>
    <section>
      <h2 class="second" :class="{ fade_up: visible.second }">Vi utvecklar våra kunder digitalt!</h2>
    </section>
    <footer class="switch">
      <h2 class="third" :class="{ fade_up: visible.third }">Color change yall</h2>
    </footer>
    <section></section>
    <section></section>
  </main>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",

  data() {
    return {
      visible: {
        first: true,
        second: false,
        third: false
      },
      scrollBefore: 0
    }
  },

  created() {
    document.addEventListener("scroll", this.animate)
  },

  methods: {
    animate() {
      setTimeout(() => {
          // if(this.inView(document.querySelector(".switch"))) {
          //   document.body.classList.add('bg')
          // }
          // else {
          //   document.body.classList.remove('bg')
          // }
          const scrolled = window.scrollY;
          if(this.scrollBefore < scrolled) {
            this.scrollBefore = scrolled;
            this.visible.first = this.inView(document.querySelector(".first"));
            this.visible.second = this.inView(document.querySelector(".second"));
            this.visible.third = this.inView(document.querySelector(".third"));
          }
        }, 100);
    },
    inView(el) {
      let windowHeight = window.innerHeight;
      let scrollY = window.scrollY || window.pageYOffset;
      let scrollPosition = scrollY + windowHeight/1.2;
      let elementPosition = el.getBoundingClientRect().top + scrollY + el.clientHeight;
      if(scrollPosition > elementPosition) return true
      else return false
    }
  },
};
</script>

<style lang="scss" scoped>

</style>
