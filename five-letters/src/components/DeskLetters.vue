<template>
  <div class="wrapper">
    <InputLetter v-model="letter" />
    <InputLetter v-model="letter" />
    <InputLetter v-model="letter" />
    <InputLetter v-model="letter" />
    <InputLetter v-model="letter" />
    <InputLetter v-model="letter" />

    <KeyboardLetters />
  </div>
</template>

<script>
import { ref } from 'vue'

import InputLetter from '@/components/controls/InputLetter.vue'
import KeyboardLetters from '@/components/keyboard/KeyboardLetters.vue'

export default {
  name: 'DeskLetters',

  components: { KeyboardLetters, InputLetter },

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
