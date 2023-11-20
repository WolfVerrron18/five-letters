<template>
  <div class="keyboard">
    <div class="keyboard__container">
      <KeyboardLettersKey
        v-for="(symbol, index) in keyboardLayout"
        :letter="symbol.character"
        :grid-area="symbol.gridArea"
        :key="index"
      >
      </KeyboardLettersKey>

      <ButtonControl class="keyboard__btn-send" :loading="false" text="dd" />
      <ButtonControl class="keyboard__btn-cross" :loading="false" text="dddd" />
      <!--      <button style="grid-area: btn-send">send</button>-->
      <!--      <button style="grid-area: btn-erase">close</button>-->
    </div>
  </div>
</template>

<script>
import KeyboardLettersKey from '@/components/keyboard/KeyboardLettersKey.vue'
import { keyboardLayout } from '@/components/keyboard/usages/keyboard.js'
import ButtonControl from '@/components/controls/ButtonControl.vue'
export default {
  name: 'KeyboardLetters',

  components: { ButtonControl, KeyboardLettersKey },

  props: {},

  setup() {
    const log = (key) => {
      console.log(key)
    }

    return { keyboardLayout, log }
  }
}
</script>

<style lang="scss" scoped>
.keyboard {
  &__container {
    display: grid;
    grid-template-areas:
      'top-1 top-2 top-3 top-4 top-5 top-6 top-7 top-8 top-9 top-10 top-11 top-12'
      'second-1 second-2 second-3 second-4 second-5 second-6 second-7 second-8 second-9 second-10 second-11 second-12'
      'send send third-2 third-3 third-4 third-5 third-6 third-7 third-8 third-9 cross cross';
    justify-items: center;
    align-items: center;
    grid-template-columns: repeat(12, 20px);
    grid-template-rows: 20px 20px;
    gap: 3px;
  }

  &__btn-send {
    height: 21px;
    width: 46px;
    grid-area: send;
  }

  &__btn-cross {
    height: 21px;
    width: 46px;
    grid-area: cross;
  }
}
</style>
