<template>
  <div class="keyboard-key" :style="{ gridArea }" @click="onClicked(symbol)">
    {{ symbol }}
  </div>
</template>

<script>
export default {
  name: 'KeyboardSymbol',

  props: {
    symbol: {
      type: String,
      default: ''
    },

    gridArea: {
      type: String,
      default: ''
    }
  },

  emits: ['onClicked'],

  setup(_, { emit }) {
    const onClicked = (character) => emit('onClicked', character)

    return { onClicked }
  }
}
</script>

<style lang="scss" scoped>
.keyboard-key {
  height: 20px;
  width: 20px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 5px;
  cursor: pointer;
  padding: 10px;
  color: white;
  background: var(--main-border-color);
  border: 1px solid var(--main-border-color);
}
</style>
