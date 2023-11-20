<template>
  <div class="keyboard-key" :style="{ gridArea }">
    {{ letter }}
  </div>
</template>

<script>
export default {
  name: 'KeyboardLettersKey',

  props: {
    letter: {
      type: String,
      default: ''
    },

    gridArea: {
      type: String,
      default: ''
    }
  },

  setup() {}
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
  background: #afaf29;
  border: 1px solid var(--main-border-color);
}
</style>
