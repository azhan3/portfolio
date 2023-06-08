<template>
  <div className="parallax-container" ref="container">
    <div className="parallax-layer layer1" ref="layer1">
      <img src="@/assets/parallax_layers/Backdrop.png" alt="Image 1">
    </div>
    <div className="parallax-layer layer2" ref="layer2">
      <img src="@/assets/parallax_layers/Layer3.png" alt="Image 2">
    </div>
    <div className="parallax-layer layer3" ref="layer3">
      <img src="@/assets/parallax_layers/Layer2.png" alt="Image 3">
    </div>
    <div className="parallax-layer layer4" ref="layer4">
      <img src="@/assets/parallax_layers/Layer1.png" alt="Image 4">
    </div>

    <div className="title-overlay" ref="title">
      <h1 className="title">Alex Zhan</h1>
    </div>
  </div>
</template>

<script>
export default {
  mounted() {
    window.addEventListener('scroll', this.parallaxScroll)
  },
  unmounted() {
    window.removeEventListener('scroll', this.parallaxScroll)
  },
  methods: {
    parallaxScroll() {
      // eslint-disable-next-line no-unused-vars
      const containerHeight = this.$refs.container.offsetHeight
      const scrollPosition = window.pageYOffset

      // Adjust the transform properties of each layer based on scroll position
      this.$refs.layer1.style.transform = `translate3d(0, ${scrollPosition * 0.3}px, 0)`
      this.$refs.layer2.style.transform = `translate3d(0, -${scrollPosition * 0.2}px, 0)`
      this.$refs.layer3.style.transform = `translate3d(-${scrollPosition * 0.2}px, 0, 0)`
      this.$refs.layer4.style.transform = `translate3d(${scrollPosition * 0.05}px, 0, 0)`

    }
  }
}
</script>

<style scoped>


.parallax-container {
  position: relative;
  height: 100vh;
  overflow: hidden;
}

.parallax-layer {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  overflow: hidden;
}

.parallax-layer img {
  display: block;
  width: 100%;
  height: auto;
}

.layer1 {
}

.layer2 {
  top: 45vh;
  right: 10vw;
}

.layer3 {
  top: 35vh;
}

.layer4 {
  top: 40vh;
}

.title-overlay {
  position: absolute;
  top: 25%;
  left: 50%;
  transform: translate(-50%, 0%);
  z-index: 2;
  text-align: center;
  width: 100%;
}

.title {
  color: #003551;
  font-size: calc(7vh + 5vw);
  font-family: Cantarell;
}
</style>
