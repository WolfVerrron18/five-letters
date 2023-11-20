<template>
  <transition name="slide" mode="out-in" appear>
    <slot />
  </transition>
</template>

<script>
export default {
  name: 'SlideTransition',

  components: {},

  props: {},

  setup() {}
}
</script>

<style lang="scss" scoped>
.slide-enter-active,
.slide-leave-active {
  transition: all 0.15s cubic-bezier(0.32, 0.67, 0.98, 0.61);
}

.slide-enter-from,
.slide-leave-to {
  position: absolute;
  opacity: 0;
  transform: scaleX(0.4);
}
</style>
