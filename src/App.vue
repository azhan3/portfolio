<template>
  <div id="app">
    <div style="background-color: #fff; height: 100vh;"></div>
    <div style="position: relative;">
      <parallax :fixed="true" :section-height="150">
        <img src="@/assets/aboutme.jpg" alt="">
      </parallax>
    </div>

    <div style="background-color: #fff; height: 100vh;"></div>
  </div>
</template>

<script>
import Parallax from './components/ParallaxSet.vue'

export default {
  name: 'app',
  components: {
    Parallax
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