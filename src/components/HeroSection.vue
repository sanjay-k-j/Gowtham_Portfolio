<template>
  <div class="hero">
    <video autoplay muted loop class="background-video">
      <source src="@/assets/background.mp4" type="video/mp4" />
    </video>
    <div class="text-content">
      <h1>Trend Investment</h1>
      <p>Grow with us</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeroSection",
};
</script>

<style scoped>
.hero {
  position: relative;
  padding: 20px;
  min-height: 400px;
  color: rgb(7, 13, 13);
}

.background-video {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover; /* Ensures the video covers the entire background */
  z-index: -1; /* Keeps the video in the background */
}

.text-content {
  position: absolute;
  top: 50%; /* Center text vertically */
  left: 50%;
  transform: translate(-50%, -50%); /* Center text horizontally and vertically */
  text-align: center;
}

.hero h1 {
  font-size: 2.5em;
  margin-bottom: 10px;
  color: rgb(15, 15, 15);
}

.hero p {
  font-size: 1.2em;
  color: #0a0a0a; /* Ensures the text is visible against the video */
}
</style>
