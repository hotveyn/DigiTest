<script setup lang="ts">
defineProps<{
  type: 'primary' | 'flat' | 'base' | 'invalid'
}>()
</script>

<template>
  <button :class="[`base-button_${type}`]" class="base-button">
    <slot />
  </button>
</template>

<style scoped lang="scss">
.base-button {
  font-size: 14px;
  border-radius: 4px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition:
    color 0.2s,
    background-color 0.2s;

  &_primary {
    border-radius: 8px;
    padding: 8px 24px;
    height: 48px;
    color: $color-black;
    border: 1px solid $color-brand;
    background-color: $color-white;
    font-family: 'Inter', sans-serif;
    font-weight: 500;

    &:hover {
      background-color: $color-brand;
      color: $color-white;
    }
  }

  &_flat {
    height: 38px;
    padding: 12px 16px;
    gap: 4px;
    border-radius: 4px;
    border: 1px solid $color-brand;
    color: $color-brand;
    background: $color-white;
    font-weight: 700;

    &:hover {
      background-color: $color-brand;
      color: $color-white;
    }
  }

  &_base {
    height: 38px;
    padding: 12px 16px;
    gap: 4px;
    border-radius: 8px;
    border: 1px solid $color-brand;
    background-color: $color-brand;
    color: $color-white;
    font-weight: 700;

    &:hover {
      border: 1px solid $color-font-hover;
      background-color: $color-font-hover;
    }
  }

  &_invalid {
    width: 100%;
    height: 38px;
    padding: 12px 16px;
    gap: 4px;
    border-radius: 4px;
    border: 1px solid $color-font-second;
    background-color: $color-white;
    color: $color-font-second;
    font-weight: 700;
  }
}
</style>
