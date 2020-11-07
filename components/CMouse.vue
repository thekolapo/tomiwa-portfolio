<template>
  <div ref="cMouse" class="c-mouse" />
</template>
<script>
export default {
  data() {
    return {
      size: null,
      event: null,
    }
  },
  mounted() {
    this.size = this.$refs.cMouse.getBoundingClientRect().width
    window.addEventListener('mousemove', this.trackCursor)
    window.addEventListener('scroll', this.handleScroll)

    const links = Array.from(document.querySelectorAll('a'))
    const buttons = Array.from(document.querySelectorAll('button'))
    const clickableElements = links.concat(buttons)
    clickableElements.forEach((element) => {
      element.addEventListener('mouseover', () => {
        this.$refs.cMouse.style.setProperty('--size', '66px')
      })
      element.addEventListener('mouseleave', () => {
        this.$refs.cMouse.style.setProperty('--size', '38px')
      })
    })
  },
  methods: {
    trackCursor(event) {
      this.$refs.cMouse.style.transform = `translate3d(${
        event.clientX - this.size / 2
      }px, ${window.scrollY + event.clientY - this.size / 2}px, 0)`
      this.event = event
    },
    handleScroll() {
      this.$refs.cMouse.style.setProperty('--trans-time', 0)
      this.trackCursor(this.event)
      clearTimeout(self.scrollTimeout)
      self.scrollTimeout = setTimeout(() => {
        // page scrolling has stopped
        this.$refs.cMouse.style.setProperty('--trans-time', '0.75s')
      }, 150)
    },
  },
}
</script>

<style lang="scss" scoped>
.c-mouse {
  --size: 40px;
  --trans-time: 0.75s;
  position: absolute;
  width: var(--size);
  height: var(--size);
  z-index: 5;
  pointer-events: none;
  top: 0;
  left: 0;
  border-radius: 50%;
  transform-origin: center;
  border: solid 1px rgb(158, 158, 158);
  transition: var(--trans-time) $easeOutExpo;
}
</style>
