<script setup lang="ts">
import IconGlass from '@/components/shared/icon/IconGlass.vue'
import { ref } from 'vue'
import IconClose from '@/components/shared/icon/IconClose.vue'
import BaseButton from '@/components/shared/button/BaseButton.vue'
const text = ref('')
</script>

<template>
  <label class="search-bar">
    <IconGlass />
    <input
      v-model="text"
      type="text"
      placeholder="Поиск по 100 000 товаров "
      class="search-bar__input w"
    />
    <template v-if="text">
      <IconClose type="grey" class="search-bar__close" />
      <BaseButton type="base"> Найти </BaseButton>
    </template>
  </label>
</template>

<style scoped lang="scss">
.search-bar {
  max-height: 48px;
  cursor: text;
  padding: 4px 4px 4px 16px;
  border: 1px $color-brand solid;
  border-radius: 10px;
  background-color: $color-white;
  @include flex();
  gap: 8px;

  &__close {
    cursor: pointer;
  }

  &__input {
    outline: none;
    border: 0;
    color: $color-font;
    font-size: 16px;
    line-height: 24px;
    font-family: Inter, sans-serif;

    &::placeholder {
      color: $color-font-second;
    }
  }
}
</style>
