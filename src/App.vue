<template>
  <div id="app">
    <ParallaxWallpaper/>
    <div style="background-color: #001A2B; height: 15vh;"></div>
    <MenuBar ref="menu"/>
    <div>
      <FadeTitle/>
    </div>
    <div>
      <parallax :fixed="fix" :section-height="110">
        <transition name="image-transition" mode="out-in">
          <img :key="path" :src="path" alt="" :class="{ 'image-fade-in': imageLoaded }" ref="image">
        </transition>
      </parallax>
    </div>
    <AboutMe ref="aboutSection" />
    <div>
      <ProjectPage ref="projectSection" />
    </div>
  </div>
</template>

<script>
import Parallax from '@/components/ParallaxSet.vue'
import ParallaxWallpaper from '@/components/Wallpapers/ParallaxWallpaper.vue'
import AboutMe from '@/components/Pages/AboutMe.vue'
import FadeTitle from "@/components/Pages/FadeTitle.vue";
import MenuBar from '@/components/MenuBar.vue';
import ProjectPage from "@/components/Pages/ProjectPage.vue";

export default {
  name: 'app',
  components: {
    Parallax,
    ParallaxWallpaper,
    AboutMe,
    FadeTitle,
    MenuBar,
    ProjectPage
  },
  data() {
    return {
      fix: true,
      path: require("@/assets/wolf-cave-minimalist-4k-s1.jpg"),
      transitioning: false
    }
  },

  mounted() {
    window.addEventListener('scroll', this.handleScroll);
  },

  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    handleScroll() {
      const scrollPosition = window.pageYOffset;
      if (scrollPosition >= 2000 && this.path !== require("@/assets/landscape___minimal_by_theninjelsama_dedubei.png")) {
        this.imageLoaded = false;

        this.path = require("@/assets/landscape___minimal_by_theninjelsama_dedubei.png");
      } else if (scrollPosition < 2000 && this.path !== require("@/assets/wolf-cave-minimalist-4k-s1.jpg")) {
        this.imageLoaded = false;
        this.path = require("@/assets/wolf-cave-minimalist-4k-s1.jpg");
      }
    }
  },
  updated() {
    this.$nextTick(() => {
      this.imageLoaded = true;
    });
  }
}
</script>

<style scoped>
body {
  margin: 0;
}
 .image-transition-enter-active,
 .image-transition-leave-active {
   transition: opacity 0.25s;
 }

.image-transition-enter {
  opacity: 0;
}

.image-transition-leave-to {
  opacity: 0;
}

.image-fade-in {
  opacity: 1;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  position: relative;
}

</style>
