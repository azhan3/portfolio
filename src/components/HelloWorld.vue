<template>
  <div>
    <!-- Parallax section -->
    <!-- Projects section -->
    <div class="projects">
      <section class="section">
        <div class="container">
          <h2>Projects</h2>
          <!-- Add your projects here -->
          <div class="project">
            <h3>Project 1</h3>
            <p>Description of project 1.</p>
          </div>
          <div class="project">
            <h3>Project 2</h3>
            <p>Description of project 2.</p>
          </div>
          <!-- Add more projects as needed -->
        </div>
      </section>
    </div>
  </div>
</template>

<script>
import M from 'materialize-css'; // Import Materialize CSS

export default {
  mounted() {
    // Initialize the parallax effect
    this.initializeParallax();
  },
  methods: {
    initializeParallax() {
      // Initialize the parallax effect on the element with class "parallax"
      const parallaxElement = document.querySelector('.parallax');
      M.Parallax.init(parallaxElement, {
        responsiveThreshold: 0
      });
    }
  }
};
</script>

<style scoped>
.parallax-container {
  height: 600px; /* Adjust the height as per your requirement */
  overflow: hidden;
  position: relative;
}

.parallax {
  background-image: url('/src/assets/wallpaper.jpeg'); /* Replace with your own image path */
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  height: 100%;
  transform: translate3d(0, 0, 0);
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}

.parallax-content {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 100%;
  padding: 0 20px;
  color: #fff;
}

.about-me,
.projects {
  width: 100%;
}

.section {
  padding: 50px 0;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
}

.project {
  margin-bottom: 20px;
}
</style>
