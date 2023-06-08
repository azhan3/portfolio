<template>
  <div id="app">
    <ParallaxWallpaper />
    <div style="background-color: #001A2B; height: 15vh;"></div>
    <MenuBar />

    <div>
      <FadeTitle />
    </div>
    <div>

      <parallax :fixed="true">
        <img ref="image" src="@/assets/wolf-cave-minimalist-4k-s1.jpg" alt="">
      </parallax>
    </div>
    <AboutMe />
    <div style="background-color: #fff; height: 100vh;"></div>
    <div style="background-color: #fff; height: 100vh;"></div>
  </div>
</template>
<script>
import Parallax from './components/ParallaxSet.vue'
import ParallaxWallpaper from './components/ParallaxWallpaper.vue'
import AboutMe from './components/AboutMe.vue'
import FadeTitle from "@/components/FadeTitle.vue";
import MenuBar from '@/components/MenuBar.vue';

export default {
  name: 'app',
  components: {
    Parallax,
    ParallaxWallpaper,
    AboutMe,
    FadeTitle,
    MenuBar
  }
}
</script>

<style>
body {
  margin: 0;
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
