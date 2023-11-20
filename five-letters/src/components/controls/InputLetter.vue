<template>
  <div class="letter__wrapper">
    <input
      v-for="letter in numberLetters"
      :key="modelValue[letter]"
      class="letter__input"
      type="text"
      maxlength="1"
      pattern="[a-zA-Z]+"
      required
      :value="modelValue[letter]"
      @input="updateLetterValue"
    />
    {{ modelValue.length }}
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'InputLetter',

  components: {},

  props: {
    modelValue: {
      type: String,
      default: ''
    }
  },

  setup() {
    const numberLetters = ref(5)

    const updateLetterValue = ({ target }) => {
      const regex = /^[А-Яа-яЁё]+$/u

      if (!regex.test(target.value)) {
        target.value = target.value.replace(/[^А-Яа-яЁё]/gu, '')
      }
    }

    return { numberLetters, updateLetterValue }
  }
}
</script>

<style lang="scss" scoped>
.letter {
  &__input {
    border: 1px solid #afaf29;
    border-radius: 5px;
    outline: none;
    width: 40px;
    height: 40px;
    font-size: 20px;
    color: #fff;
    text-align: center;
    background: transparent;

    &:not(:last-child) {
      margin-right: 5px;
    }
  }
}
</style>
