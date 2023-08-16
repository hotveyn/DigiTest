<script setup lang="ts">
import IconClose from '@/components/shared/icon/IconClose.vue'
import { ref } from 'vue'
import BaseButton from '@/components/shared/button/BaseButton.vue'

const text = ref('')
withDefaults(
  defineProps<{
    typeX: 'base' | 'secondary'
  }>(),
  { typeX: 'base' }
)
</script>

<template>
  <label :class="[`base-input_${typeX}`]" class="base-input w">
    <span v-if="typeX !== 'secondary'" class="base-input__left"><slot name="left" /></span>
    <input v-model="text" v-bind="$attrs" class="base-input__input w" />
    <IconClose v-if="text" type="grey" />
    <template v-if="typeX === 'secondary'">
      <BaseButton class="base-input__button" type="base">Поиск</BaseButton>
    </template>
  </label>
</template>

<style scoped lang="scss">
.base-input {
  max-height: 36px;
  cursor: text;
  padding: 10px 8px;
  border: 1px $color-border solid;
  border-radius: 4px;
  background-color: $color-white;
  @include flex();
  gap: 6px;

  &_secondary {
    max-height: unset;
    height: 45px;
    border: 0;
    border-radius: 0;
    border-bottom: 1px $color-border solid;
    padding: 0;
  }

  &__left {
    font-size: 12px;
    font-style: normal;
    font-weight: 400;
    line-height: 14px;
    color: $color-font-second;
    user-select: none;
  }

  &__input {
    outline: none;
    border: 0;
    color: $color-font;
    font-size: 14px;
    line-height: 16px;

    &::placeholder {
      color: $color-font-second;
    }

    &::-webkit-outer-spin-button,
    &::-webkit-inner-spin-button {
      -webkit-appearance: none;
      margin: 0;
    }
  }

  &__button {
    max-height: 38px;
  }
}
</style>
