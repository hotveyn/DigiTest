<script setup lang="ts">
defineProps<{
  type: 'parent' | 'child'
  active?: boolean
}>()
</script>

<template>
  <button :class="[`category_${type}`, { category_active: active }]" class="category w">
    <span class="category__name"><slot name="name" /></span>
    <span class="category__count"><slot name="count" /></span>
  </button>
</template>

<style scoped lang="scss">
.category {
  cursor: pointer;
  background-color: $color-white;
  border: 0;
  outline: 0;
  border-radius: 5px;
  @include flex(space-between);
  height: 30px;

  &_parent {
    padding: 0 16px 0 8px;
  }

  &_child {
    padding: 0 16px 0 32px;
  }

  &:hover {
    background-color: $color-font-bg;

    &__count {
      color: $color-font;
    }
  }

  &:hover &__count {
    color: $color-font;
  }

  &_active {
    background-color: $color-font-bg;

    &__count {
      color: $color-font;
    }
  }

  &_active &__count {
    color: $color-font;
  }

  &__name {
    width: fit-content;
    color: $color-font;
    font-size: 14px;
  }

  &__count {
    width: fit-content;
    font-size: 12px;
    color: $color-font-second;
  }
}
</style>
