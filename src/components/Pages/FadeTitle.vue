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
    window.addEventListener('scroll', this.handleScroll);
  },

  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    toggle() {
      this.show = !this.show;
    },
    handleScroll() {
      const scrollPosition = window.pageYOffset;
      if (scrollPosition > 500 && scrollPosition <= 1200) {
        if (!this.show) {
          this.toggle();
        }
      } else if (scrollPosition > 1200) {
        if (this.show) {
          this.toggle();
        }
      } else if (scrollPosition < 500) {
        if (this.show) {
          this.toggle();
        }
      }
    }

  }
};
</script>

<style scoped>
h2 {
  font-size: calc(4vh + 6vw);
  color: white;
  position: absolute;
  margin-top: 50vh;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 20;
  text-transform: uppercase;
  font-weight: 3000;
  letter-spacing: 3px;
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
