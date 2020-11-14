<template>
  <div ref="imgLoader" class="c-image-loader">
    <div class="c-image-loader__container">
      <div class="c-image-loader__counter">
        <span>{{ counter }}</span>
        <div class="c-image-loader__overlay"></div>
      </div>
      <svg
        class="c-image-loader__stroke"
        viewBox="0 0 120 120"
        fill="transparent"
      >
        <circle cx="60" cy="60" r="59.5" stroke="black" stroke-width="0.5" />
      </svg>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      counter: 0,
    }
  },
  mounted() {
    this.startCounter()
  },
  methods: {
    startCounter() {
      setTimeout(() => {
        this.counter = 20
        const counter = setInterval(() => {
          this.counter += 20

          if (this.counter === 80) clearInterval(counter)
        }, 150)
      }, 1000)
    },
    completeLoaderAnim() {
      setTimeout(() => {
        this.counter = 100
        this.$refs.imgLoader.style.setProperty('--text-translate-value', '100%')
        this.$refs.imgLoader.style.setProperty('--stroke-dashoffset', '375')
        this.hideImgLoader()
      }, 1800)
    },
    hideImgLoader() {
      setTimeout(() => {
        this.$parent.hideImgLoader()
      }, 1500)
    },
  },
}
</script>

<style lang="scss" scoped>
.c-image-loader {
  position: absolute;
  width: 100vw;
  height: 100vh;
  background-color: var(--bg-color);
  top: 0;
  z-index: 10;
  display: flex;
  // align-items: center;
  justify-content: center;
  --text-anim-duration: 1s;
  --text-translate-value: 0%;
  --stroke-length: 375;
  --stroke-dashoffset: 0;

  @keyframes slideup {
    from {
      transform: translateY(100%);
    }
  }

  @keyframes drawcircle {
    from {
      stroke-dashoffset: var(--stroke-length);
    }
  }

  @keyframes reveal {
    to {
      opacity: 1;
    }
  }

  &__container {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    display: flex;
    align-items: center;
    justify-content: center;

    @include screen('small') {
      top: 40%;
    }
  }

  &__counter {
    position: relative;
    font-size: 3.5rem;
    font-family: 'Canela';
    font-variant-numeric: tabular-nums;

    span {
      display: inline-block;
      z-index: 1;
      transform: translateY(var(--text-translate-value));
      transition: transform $easeOutExpo var(--text-anim-duration) 1s;
      animation: slideup var(--text-anim-duration) $easeOutExpo;

      &:after {
        content: '%';
      }
    }
  }

  &__overlay {
    position: absolute;
    width: 100%;
    height: 100%;
    top: 0;
    left: 0;
    background-color: var(--bg-color);
    z-index: 2;
    background-color: var(--bg-color);
    transform: translateY(100%);
  }

  &__stroke {
    $size: 170px;
    $transition-duration: 0.6s;
    position: absolute;
    z-index: 3;
    width: $size;
    height: $size;
    opacity: 0;
    stroke-dasharray: var(--stroke-length);
    stroke-dashoffset: var(--stroke-dashoffset);
    transform: rotate(-90deg);
    transition: $transition-duration ease-out 0.5s;
    animation: drawcircle $transition-duration ease-out
        calc(var(--text-anim-duration) - #{$transition-duration}),
      reveal 0s linear
        calc(var(--text-anim-duration) - #{$transition-duration} + 50ms)
        forwards;
  }
}
</style>
