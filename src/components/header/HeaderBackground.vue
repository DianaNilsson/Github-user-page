<template>
  <div class="header-background">
    <div class="bg-img"></div>
    <div class="fog-overlay">
      <div class="fog-img fog-img-first"></div>
      <div class="fog-img fog-img-second"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeaderBackground"
};
</script>

<style scoped>
.bg-img {
  position: absolute;
  top: 0;
  left: 0;
  height: 100vh;
  width: 100vw;
  background: #819582 url("../../assets/background.jpg") no-repeat 50%;
  background-size: cover;
}

.fog-overlay {
  position: absolute;
  height: 100vh;
  width: 100vw;
}

.fog-img {
  position: absolute;
  height: 100vh;
  width: 300vw;

  background-repeat: repeat-x;
  background-size: cover;
  background-position: center;
}

.fog-img-first {
  background: url("../../assets/fog-1.png");
  background-size: contain;
  animation: marquee 100s linear infinite;
}

.fog-img-second {
  background: url("../../assets/fog-2.png");
  background-size: contain;
  animation: marquee 40s linear infinite;
}

@keyframes marquee {
  0% {
    transform: translate3d(0, 0, 0);
  }
  100% {
    transform: translate3d(-200vw, 0, 0);
  }
}
</style>