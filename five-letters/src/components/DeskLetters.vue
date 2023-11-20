<template>
  <div class="wrapper">
    <InputLetter v-model="letter" />
    <InputLetter v-model="letter" />
    <InputLetter v-model="letter" />
    <InputLetter v-model="letter" />
    <InputLetter v-model="letter" />
    <InputLetter v-model="letter" />

    <KeyboardSymbols />
  </div>
</template>

<script>
import { ref } from 'vue'

import InputLetter from '@/components/controls/InputLetter.vue'
import KeyboardSymbols from '@/components/keyboard/KeyboardSymbols.vue'

export default {
  name: 'DeskLetters',

  components: { KeyboardSymbols, InputLetter },

  props: {},

  setup() {
    const letter = ref('')

    return {
      letter
    }
  }
}
</script>

<style lang="scss" scoped>
.wrapper {
}
</style>
