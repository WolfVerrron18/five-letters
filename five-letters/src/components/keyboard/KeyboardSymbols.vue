<template>
  <div class="keyboard">
    <!-- Клавиатура -->
    <div class="keyboard__container">
      <!-- Символ -->
      <KeyboardSymbol
        v-for="(symbol, index) in keyboardLayout"
        :symbol="symbol.symbol"
        :grid-area="symbol.gridArea"
        :key="index"
        @on-clicked="selectedSymbol"
      />

      <!-- Кнопка отправки -->
      <ButtonControl class="keyboard__btn-send" :loading="loading" @on-clicked="sendWord">
        <!-- Иконка галочки -->
        <template #icon>
          <SvgCheckMark />
        </template>
      </ButtonControl>

      <!-- Кнопка стереть -->
      <ButtonControl class="keyboard__btn-cross">
        <!-- Иконка крестика -->
        <template #icon>
          <SvgCross />
        </template>
      </ButtonControl>
    </div>
  </div>
</template>

<script>
import KeyboardSymbol from '@/components/keyboard/KeyboardSymbol.vue'
import { keyboardLayout } from '@/components/keyboard/usages/keyboard.js'
import ButtonControl from '@/components/controls/ButtonControl.vue'
import SvgCross from '@/components/Icons/SvgCross.vue'
import SvgCheckMark from '@/components/Icons/SvgCheckMark.vue'
import { ref } from 'vue'
export default {
  name: 'KeyboardSymbols',

  components: { SvgCheckMark, SvgCross, ButtonControl, KeyboardSymbol },

  props: {},

  setup() {
    const loading = ref(false)

    const selectedSymbol = (symbol) => {
      console.log(symbol)
    }

    const sendWord = () => {
      loading.value = true

      return new Promise((resolve) => {
        setTimeout(() => {
          loading.value = false
          resolve()
        }, 1000)
      })
    }

    return { loading, keyboardLayout, selectedSymbol, sendWord }
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
    height: 21.6px;
    width: 40px;
    grid-area: send;
  }

  &__btn-cross {
    height: 21.6px;
    width: 40px;
    grid-area: cross;
  }
}
</style>
