<template>
  <div class="error-container font-weight-bold text-center">
    <div id="error">
      <div>404</div>
      <div>404</div>
      <div>404</div>
      <div>404</div>
      <div>404</div>
    </div>
  </div>

  <div class="text-body-2 font-weight-light">
    The requested page has not been found
  </div>

  <div class="py-14" />
</template>

<script setup>
//
</script>

<style lang="scss" scoped>
.error-container {
  --glitch-duration: 3s;
  font-size: 160px;
  height: 160px;
}

#error {
  position: relative;
  width: 100%;
  height: 100%;
}

#error > div {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  z-index: 1;
}
#error > div::before {
  content: "404";
  position: absolute;
  left: 3px;
  color: yellow;
  opacity: 1;
  z-index: -1;
}
#error > div::after {
  content: "404";
  position: absolute;
  left: 2px;
  color: pink;
  opacity: 1;
  z-index: -1;
}

#error > div:nth-child(1) {
  animation: glitch1 var(--glitch-duration) infinite steps(1, end);
}
#error > div:nth-child(2) {
  animation: glitch2 var(--glitch-duration) infinite steps(1, end);
}
#error > div:nth-child(3) {
  animation: glitch3 var(--glitch-duration) infinite steps(1, end);
}
#error > div:nth-child(4) {
  animation: glitch4 var(--glitch-duration) infinite steps(1, end);
}
#error > div:nth-child(5) {
  animation: glitch5 var(--glitch-duration) infinite steps(1, end);
}

@keyframes glitch1 {
  20% {
    clip-path: polygon(0 0%, 100% 0%, 100% 33%, 0 33%);
    transform: translate(-50%, -50%);
  }
  30% {
    clip-path: polygon(0 0, 0 100%, 100% 100%, 100%, 0);
    transform: translate(-50%, -50%);
  }
  47% {
    transform: translate(-45%, -45%);
  }
  48% {
    transform: translate(-50%, -50%);
  }
  49% {
    transform: translate(-55%, -45%);
  }
  50% {
    transform: translate(-50%, -50%);
  }
}

@keyframes glitch2 {
  0% {
    opacity: 0;
  }
  20% {
    opacity: 1;
    clip-path: polygon(0 40%, 100% 40%, 100% 60%, 0% 60%);
    transform: translate(-50%, -50%);
  }
  21% {
    transform: translate(-46%, -46%);
  }
  22% {
    transform: translate(-54%, -54%);
  }
  30% {
    clip-path: polygon(0 0, 0 100%, 100% 100%, 100%, 0);
    transform: translate(-50%, -50%);
  }
  35% {
    transform: translate(-45%, -55%);
  }
  36% {
    transform: translate(-50%, -50%);
  }
  37% {
    transform: translate(-40%, -45%);
  }
  38% {
    transform: translate(-50%, -50%);
  }
  50% {
    transform: translate(-45%, -55%);
  }
  51% {
    transform: translate(-50%, -60%);
  }
  52% {
    transform: translate(-45%, -50%);
  }
  53% {
    transform: translate(-50%, -50%);
  }
  71% {
    transform: translate(-40%, -60%);
  }
  72% {
    transform: translate(-45%, -50%);
  }
  73% {
    transform: translate(-40%, -50%);
  }
  77% {
    transform: translate(-50%, -50%);
  }
}

@keyframes glitch3 {
  0% {
    opacity: 0;
  }
  20% {
    opacity: 1;
    clip-path: polygon(0 70%, 100% 70%, 100% 100%, 0% 100%);
    transform: translate(-50%, -50%);
  }
  30% {
    transform: translate(-40%, -40%);
  }
  31% {
    transform: translate(-50%, -50%);
  }
  35% {
    clip-path: polygon(0 0, 0 100%, 100% 100%, 100%, 0);
    transform: translate(-50%, -50%);
  }
  45% {
    transform: translate(-60%, -60%);
  }
  46% {
    transform: translate(-50%, -50%);
  }
  47% {
    clip-path: polygon(0 0, 0 100%, 100% 100%, 100%, 0);
    transform: translate(-50%, -50%);
  }
  69% {
    transform: translate(-40%, -40%);
  }
  71% {
    transform: translate(-50%, -50%);
  }
}

@keyframes glitch4 {
  0% {
    opacity: 0;
  }
  22% {
    opacity: 1;
    clip-path: polygon(0 32%, 100% 32%, 100% 41%, 0% 41%);
    transform: translate(-48%, -50%);
  }
  24% {
    clip-path: polygon(0 0, 0 100%, 100% 100%, 100%, 0);
    transform: translate(-50%, -50%);
  }
}

@keyframes glitch5 {
  0% {
    opacity: 0;
  }
  20% {
    opacity: 1;
    clip-path: polygon(0 59%, 100% 59%, 100% 71%, 0% 71%);
    transform: translate(-52%, -50%);
  }
  25% {
    clip-path: polygon(0 0, 0 100%, 100% 100%, 100%, 0);
    transform: translate(-50%, -50%);
  }
}
</style>