<template>
  <div class="about-me">
    <div class="container">
      <div class="content">
        <div class="profile-image">
          <img src="@/assets/profile-image.png" alt="Profile Image">
        </div>
        <div class="text">
          <h3>
            Hey there!
          </h3>
          <h4>
            I'm Alex, a grade 11 high school student from Ottawa.
          </h4>
          Passionate, curious, and always up for a challenge, I love exploring the endless possibilities that the world has to offer.I enjoy the thrill of problem-solving, whether it's tackling complex puzzles or diving into competitive programming. There's a certain satisfaction that comes with unraveling a tricky challenge and finding innovative solutions. It's a constant journey of learning, growth, and expanding my horizons.
          <p>
            When I'm not coding, you'll find me exploring the great outdoors, whether it's skiing down snowy slopes, hiking through scenic trails, or challenging opponents on the volleyball court.          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.about-me {
  background-color: #f9f9f9;
  padding: 50px 0;
  text-align: center;
}

.container {
  max-width: 800px;
  margin: 0 auto;
}

h2 {
  font-size: 32px;
  margin-bottom: 20px;
}

.content {
  display: flex;
  justify-content: center;
  align-items: center;
}

.profile-image {
  flex: 0 0 200px;
  margin-right: 30px;
}

.profile-image img {
  width: 100%;
  border-radius: 50%;
}

.text {
  flex: 1;
  text-align: left;
}

.text p {
  margin-bottom: 20px;
}
</style>
<script setup>
</script>