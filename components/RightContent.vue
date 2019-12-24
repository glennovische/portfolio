<template>
  <div :class="imageClass" class="image">
    <div class="image__over">
      <div class="image__cover"></div>
      <div class="image__cover"></div>
    </div>
    <div class="page-num">
      <p><slot name="number"></slot></p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    imageClass: {
      type: String,
      default: ''
    }
  }
}
</script>

<style lang="scss" scoped>
.image {
  display: block;
  position: relative;
  width: 53.125%;
  height: 74.81%;
  margin: 0 8% 0 auto;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
  box-shadow: 0 80px 140px -40px rgba(0, 0, 0, 0.6);
  animation-name: Zoomer;
  animation-duration: 1.5s;
  &__over {
    width: 100%;
    height: 100%;
    overflow: hidden;
    position: relative;
  }
  &__cover {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    right: 0;
    background: #ff4d5a;
    transform: translateX(110%) translateZ(0px);
    animation-name: LeftRightOut;
    animation-duration: 1.5s;
    &:last-child {
      animation-name: LeftRightOut;
      animation-duration: 1s;
      background: #072142;
    }
  }

  &--works {
    background-image: url('../assets/img/reile.jpg');
  }

  &--design {
    background-image: url('../assets/img/about.jpg');
  }

  &--about {
    background-image: url('../assets/img/contact.jpg');
  }

  .page-num {
    font-family: 'Abril Fatface', cursive;
    position: absolute;
    overflow-y: hidden;
    right: -7.549%;
    bottom: 12.3762%;
    font-size: 15rem;
    color: #fff;
    z-index: 200;
    animation-name: BottomToTop;
    animation-duration: 1.5s;
    p {
      line-height: 1.1;
      text-shadow: 0 10px 30px rgba(2, 11, 22, 0.5);
    }
  }
}

@keyframes LeftRightOut {
  from {
    transform: translateX(0%) translateZ(0px);
  }
  to {
    transform: translateX(110%) translateZ(0px);
  }
}

@keyframes BottomToTop {
  from {
    transform: translateY(100%) translateZ(0px);
  }
  to {
    transform: translateY(0%) translateZ(0px);
  }
}

@keyframes Zoomer {
  from {
    transform: scale(0.85) translateX(10%) translateZ(0px);
  }
  to {
    transform: scale(1) translateX(0%) translateZ(0px);
  }
}
</style>
