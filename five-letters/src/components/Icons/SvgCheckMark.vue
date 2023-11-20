<template>
  <svg :width="width" :height="height" fill="white" class="bi bi-check2" viewBox="0 0 16 16">
    <path
      d="M13.854 3.646a.5.5 0 0 1 0 .708l-7 7a.5.5 0 0 1-.708 0l-3.5-3.5a.5.5 0 1 1 .708-.708L6.5 10.293l6.646-6.647a.5.5 0 0 1 .708 0z"
    />
  </svg>
</template>

<script>
export default {
  name: 'SvgCheckMark',

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
    }
  },

  setup() {}
}
</script>

<style lang="scss" scoped></style>
