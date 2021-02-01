<template>
  <main class="home">
    <header >
      <h1 class="fade">
        <span>A</span>
        <span>F</span>
        <span>O</span>
        <span>N</span>
        <span>S</span>
        <span>O</span>
      </h1>
    </header>
    <section>
      <h2 v-scrolll="handleScrollOne">Vi utvecklar våra kunder digitalt!</h2>
    </section>
    <footer class="switch">
      <h2 v-scrolll="handleScroll">Color change yall</h2>
    </footer>
    <section></section>
    <section></section>
  </main>
</template>

<script>
import scrolll from '@/directives/scroll';
import {debounce} from '@/helpers/debounce'


export default {
  name: "Home",

  directives: {
    scrolll: scrolll
  },

  methods: {
    handleScroll: debounce(function (e, el) {
      console.log(el)
      if(this.inView(el)) {
        el.classList.add('fade_up')
      }
    }, 50),
    handleScrollOne: debounce(function (e, el) {
      console.log(el)
      if(this.inView(el)) {
        el.classList.add('fade_up')
      }
    }, 50),

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
