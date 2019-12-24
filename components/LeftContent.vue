<template>
  <div class="title">
    <h2
      class="title__text js-letter"
      style="transform: translateX(0%) translateZ(0px);"
    >
      <slot name="title"></slot>
    </h2>
    <div
      class="border js-letter"
      style="transform: translateX(0%) translateZ(0px);"
    >
      <span></span
      ><span
        class="js-letter"
        style="transform: translateX(0%) translateZ(0px);"
      ></span>
    </div>
    <p
      class="title__subtitle js-letter"
      style="transform: translateX(0%) translateZ(0px);"
    >
      <slot name="subtitle"></slot>
    </p>
    <div
      class="btn-wrap js-letter"
      style="transform: translateX(0%) translateZ(0px);"
    >
      <slot name="content"></slot>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style lang="scss" scoped>
@import '~/assets/scss/_colors.scss';

.js-letter {
  animation-name: LeftRightIn;
  animation-duration: 1.5s;
}

.title {
  color: $white;
  position: absolute;
  overflow: hidden;
  top: 50%;
  transform: translate3d(0, -50%, 0);
  z-index: 200;
  margin-left: 11%;
  &__text {
    font-size: 120px;
    line-height: 1;
    letter-spacing: 0.1em;
    margin-bottom: 1.6rem;
    font-weight: bold;
    text-shadow: 0 10px 30px rgba(2, 11, 22, 0.5);
  }

  &__subtitle {
    color: $white;
    font-size: 28px;
    line-height: 1.5;
    letter-spacing: 0.1em;
  }

  .border {
    border: 0 !important;
    display: inline-block;
    margin-bottom: 3.2rem;
    span {
      display: block;
      width: 88px;
      height: 4px;
      border-radius: 5px;
      background: $secondary;
      &:first-child {
        margin-bottom: 1.4rem;
      }
      &:last-child {
        margin-left: 54px;
      }
    }
  }
}

@keyframes LeftRightIn {
  from {
    transform: translateX(-105%) translateZ(0px);
  }
  to {
    transform: translateX(0%) translateZ(0px);
  }
}
</style>
