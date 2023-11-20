<template>
  <svg class="loader" viewBox="0 0 50 50" :width="width" :height="height">
    <circle class="loader__path" :stroke="stroke" cx="25" cy="25" r="20" fill="none"></circle>
  </svg>
</template>

<script>
export default {
  name: 'SvgLoader',

  components: {},

  props: {
    /** @property {number} width - Ширина иконки */
    width: {
      type: Number,
      default: 16
    },

    /** @property {number} height - Высота иконки */
    height: {
      type: Number,
      default: 16
    },

    /** @property {string} stroke - Заливка спиннера */
    stroke: {
      type: String,
      default: 'RoyalBlue'
    }
  },

  setup() {}
}
</script>

<style lang="scss" scoped>
.loader {
  display: inline;
  animation: rotateSpinner 2s linear infinite;

  &__path {
    animation: loadingSpinner 1.5s ease-in-out infinite;
    stroke-dasharray: 90, 150;
    stroke-dashoffset: 0;
    stroke-width: 2;
    stroke-linecap: round;
  }
}

@keyframes loadingSpinner {
  0% {
    stroke-dasharray: 1, 200;
    stroke-dashoffset: 0;
  }

  50% {
    stroke-dasharray: 90, 150;
    stroke-dashoffset: -40px;
  }
  100% {
    stroke-dasharray: 90, 150;
    stroke-dashoffset: -120px;
  }
}

@keyframes rotateSpinner {
  100% {
    transform: rotate(360deg);
  }
}
</style>
