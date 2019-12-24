<template>
  <div
    class="loader"
    style="transform: translateY(-100%) translateZ(0px);"
  ></div>
</template>

<style lang="scss" scoped>
.loader {
  position: fixed;
  width: 100%;
  height: 150%;
  background: #020b16;
  top: 0;
  left: 0;
  z-index: 9999;
  animation-name: BottomToTop;
  animation-duration: 1.5s;
}

@keyframes BottomToTop {
  from {
    transform: translateY(0%) translateZ(0px);
  }
  to {
    transform: translateY(-100%) translateZ(0px);
  }
}
</style>
