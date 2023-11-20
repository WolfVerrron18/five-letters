<template>
  <div class="button-control" @click="onClicked">
    <SlideTransition>
      <slot name="icon" v-if="!showText && !loading" />
    </SlideTransition>

    <SlideTransition>
      <SvgLoader v-if="loading" :stroke="strokeSpinner" />
    </SlideTransition>

    <SlideTransition>
      <p v-if="showText && !loading" class="button-control__text">{{ text }}</p>
    </SlideTransition>
  </div>
</template>

<script>
import SvgLoader from '@/components/Icons/SvgLoader.vue'
import SlideTransition from '@/components/transitions/SlideTransition.vue'

export default {
  name: 'ButtonControl',

  components: { SlideTransition, SvgLoader },

  props: {
    showText: {
      type: Boolean,
      default: false
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
    },

    strokeSpinner: {
      type: String,
      default: 'white'
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
