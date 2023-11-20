<template>
  <div class="button-control" @click="onClicked">
    <slot name="icon" v-if="!showText && !loading" />

    <SvgLoader v-if="loading" />

    <p v-else-if="showText && !loading" class="button-control__text">{{ text }}</p>
  </div>
</template>

<script>
import SvgLoader from '@/components/Icons/SvgLoader.vue'

export default {
  name: 'ButtonControl',

  components: { SvgLoader },

  props: {
    showText: {
      type: Boolean,
      default: true
    },

    text: {
      type: String,
      default: ''
    },

    loading: {
      type: Boolean,
      default: false
    },

    disabled: {
      type: Boolean,
      default: false
    }
  },

  emits: ['onClicked'],

  setup(props, { emit }) {
    const onClicked = () => emit('onClicked')

    return { onClicked }
  }
}
</script>

<style lang="scss" scoped>
.button-control {
  background: transparent;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 4px;
  border: 1px solid var(--main-border-color);
  cursor: pointer;
}
</style>
