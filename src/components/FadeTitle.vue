<template>
  <div>
    <transition name="slide-fade">
      <h2 class="fade" v-if="show" className="about-me-header">About Me</h2>
    </transition>
  </div>
</template>

<script>
export default {
  data() {
    return {
      show: false
    }
  },

  mounted() {
    // Attach the scroll event listener
    window.addEventListener('scroll', this.handleScroll);
  },

  beforeUnmount() {
    // Remove the scroll event listener to prevent memory leaks
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    toggle() {
      this.show = !this.show;
    },
    handleScroll() {
      const scrollPosition = window.pageYOffset;
      if (scrollPosition > 500 && scrollPosition <= 1200) {
        if (!this.show) { // Only toggle if it's not already toggled
          this.toggle();
        }
      } else if (scrollPosition > 1200) {
        if (this.show) { // Only toggle if it's already toggled
          this.toggle();
        }
      } else if (scrollPosition < 500) {
        if (this.show) { // Only toggle if it's already toggled
          this.toggle();
        }
      }
    }

  }
};
</script>

<style>
h2 {
  font-size: calc(4vh + 6vw);
  color: white;
  position: absolute; /* Position the title absolutely within its containing element */
  margin-top: 45vh;
  left: 50%; /* Adjust the left position as needed */
  transform: translate(-50%, -50%); /* Center the title vertically and horizontally */
  z-index: 20; /* Ensure the title appears above the parallax wallpaper */

}


.slide-fade-enter-active {
  transition: all 0.8s ease-out;
}

.slide-fade-leave-active {
  transition: all 1.2s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(20px);
  opacity: 0;
}
</style>
