<template>
  <div class="about-wrapper">
    <div class="about-left">
      <div class="about-left-content">
        <div>
          <div class="shadow">
            <div class="about-img">
              <img src="@/assets/profile-image.png" alt="about image">
            </div>
          </div>

          <h2>Alex Zhan</h2>
          <h3>Student</h3>
        </div>

        <ul class="icons">
          <li><i class="fab fa-facebook-f"></i></li>
          <li><i class="fab fa-twitter"></i></li>
          <li><i class="fab fa-linkedin"></i></li>
          <li><i class="fab fa-instagram"></i></li>
        </ul>
      </div>
    </div>

    <div class="about-right">
      <h1>Hello<span>!</span></h1>
      <h2>I'm Alex, a grade 11 high school student from Ottawa.</h2>
      <div class="about-btns">
        <button type="button" class="btn btn-blue">resume</button>
        <button type="button" class="btn btn-white">projects</button>
      </div>

      <div class="about-para">
        <p>Passionate, curious, and always up for a challenge, I love exploring the endless possibilities that the world
          has to offer.I enjoy the thrill of problem-solving, whether it's tackling complex puzzles or diving into
          competitive programming. There's a certain satisfaction that comes with unraveling a tricky challenge and
          finding innovative solutions. It's a constant journey of learning, growth, and expanding my horizons.</p>
        <p>
          When I'm not coding, you'll find me exploring the great outdoors, whether it's skiing down snowy slopes,
          hiking through scenic trails, or challenging opponents on the volleyball court. </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'AboutPage'
};
</script>
<style>

@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@200;300;400;500;600;700;800&display=swap');

</style>
<style scoped>

* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

body {
  font-family: 'Poppins', sans-serif;
}

.about-wrapper {
  height: 100vh;
}

.about-left {
  background: #001A2B;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.about-left-content > div {
  background: #90C6F4;
  padding: 4rem 4rem 2.5rem 5rem;
  text-align: center;
}

.about-left-content {
  box-shadow: 0px 0px 18px -1px rgba(0, 0, 0, 0.39);
  -webkit-box-shadow: 0px 0px 18px -1px rgba(0, 0, 0, 0.39);
  -moz-box-shadow: 0px 0px 18px -1px rgba(0, 0, 0, 0.39);
}

.about-img img {
  display: block;
  width: 200px;
}

.about-img {
  width: 200px;
  height: 200px;
  overflow: hidden;
  border-radius: 50%;
  transition: all 0.5s ease-in-out;
}

.shadow {
  margin-left: auto;
  margin-right: auto;
  border-radius: 50%;
  width: 200px;
  height: 200px;
  position: relative;
  cursor: pointer;
}

.shadow::after {
  content: "";
  position: absolute;
  background: rgba(0, 0, 0, 0.4);
  left: 50%;
  transform: translateX(-50%);
  bottom: -20px;
  height: 7px;
  width: 50px;
  filter: blur(3px);
  -webkit-filter: blur(3px);
  opacity: 0;
  transition: all 0.6s ease;
}

.shadow:hover .about-img {
  transform: translateY(-10px);
}

.shadow:hover::after {
  opacity: 1;
}

.about-left-content h2 {
  font-size: 2rem;
  margin: 2.2rem 0 0.6rem 0;
  line-height: 1.2;
  padding-bottom: 1rem;
  border-bottom: 2px solid #edffec;
}

.about-left-content h3 {
  text-transform: uppercase;
  font-weight: 300;
  letter-spacing: 10px;
  margin-top: 1.2rem;
}

.icons {
  background: #fff;
  display: flex;
  justify-content: center;
  padding: 0.8rem 0;
}

.icons li {
  list-style-type: none;
  background: #3D68C2;
  color: #fff;
  width: 40px;
  height: 40px;
  margin: 0 0.5rem;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 1.2rem;
  cursor: pointer;
  transition: all 0.5s ease-in-out;
}

.icons li:hover {
  background: #90C6F4;
  color: #000;
}

.about-right {
  background: rgba(255, 255, 255, 0.9);
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding: 0 5rem;
  text-align: center;
}

.about-right h1 {
  font-size: 7rem;
  text-transform: uppercase;
}

.about-right h1 span {
  color: #8DB0E8;
}

.about-right h2 {
  font-weight: 600;
}

.about-btns {
  display: flex;
  margin: 2rem 0;
}

.btn {
  border: none;
  font-size: 0.9rem;
  text-transform: uppercase;
  border: 2px solid #000;
  border-radius: 20px;
  padding: 0.55rem 0;
  width: 130px;
  font-weight: 600;
  background: transparent;
  margin: 0 0.5rem;
  cursor: pointer;
}

.btn.btn-blue {
  background: #8DB0E8;
  color: #fff;
  border-color: #8DB0E8;
  transition: all 0.5s ease-in-out;
}

.btn.btn-blue:hover {
  background: transparent;
  border-color: #8DB0E8;
  color: #000;
}

.btn.btn-white {
  transition: all 0.5s ease-in-out;
}

.btn.btn-white:hover {
  background: #8DB0E8;
  border-color: #8DB0E8;
  color: #fff;
}

.about-para p {
  font-weight: 300;
  padding: 0.5rem;
  opacity: 0.8;
}

@media screen and (min-width: 992px) {
  .about-wrapper {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
  }

  .about-left {
    position: relative;
  }

  .about-left-content {
    position: absolute;
    right: -50px;
  }
}
</style>
