<template>
  <div class="menu-bar" :class="{ 'sticky': isSticky }">
    <nav>
      <ul>
        <li @click="navigate('about')">About Me</li>
        <li @click="navigate('portfolio')">Portfolio</li>
        <li @click="navigate('contact')">Contact</li>
      </ul>
    </nav>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isSticky: false,
      OriPos: 0
    };
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll);
    this.OriPos = this.$el.offsetTop;
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll);
  },
  methods: {
    navigate(section) {
      const sectionRef = `${section}Section`;
      console.log(sectionRef);
      console.log(this.$parent.$refs[sectionRef].$el.offsetTop);
      if (this.$parent.$refs[sectionRef]) {
        this.$parent.$refs[sectionRef].$el.scrollIntoView({ behavior: 'smooth' });
      }
    },
    handleScroll() {
      const scrollPosition = window.pageYOffset;
      this.isSticky = scrollPosition > this.$el.offsetTop;

      this.isSticky = scrollPosition > this.OriPos;
    }
  }
};
</script>

<style scoped>
.menu-bar {
  background-color: #001A2B;
  height: 10vh;
  display: flex;
  justify-content: center;
  align-items: center;
  transition: top 0.3s;
  z-index: 999;
}

.sticky {
  position: fixed;
  top: 0;
  width: 100%;
}

.menu-bar nav ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
  display: flex;
  justify-content: center;
}

.menu-bar nav ul li {
  margin: 0 10px;
  color: white;
  cursor: pointer;
}

.menu-bar nav ul li:hover {
  text-decoration: underline;
}
</style>
