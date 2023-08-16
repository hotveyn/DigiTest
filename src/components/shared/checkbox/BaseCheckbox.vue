<script setup lang="ts"></script>

<template>
  <label class="checkbox w">
    <input type="checkbox" class="checkbox__input" v-bind="$attrs" />
    <span class="checkbox__custom" />
    <span class="checkbox__left"><slot name="left" /></span>
    <span class="checkbox__count"><slot name="count" /></span>
  </label>
</template>

<style scoped lang="scss">
.checkbox {
  @include flex(space-between);
  position: relative;
  padding-left: 35px;
  padding-right: 16px;
  height: 20px;
  cursor: pointer;
  user-select: none;
  font-size: 17px;

  &__count {
    font-size: 12px;
    color: $color-font-second;
  }

  &__left {
    font-size: 14px;
    color: $color-font;
  }

  &__input {
    position: absolute;
    opacity: 0;
    cursor: pointer;
    visibility: hidden;
    height: 0;
    width: 0;
  }

  &__custom {
    border-radius: 4px;
    position: absolute;
    top: 0;
    left: 0;
    height: 20px;
    width: 20px;
    background-color: $color-white;
    outline: 1px $color-border solid;

    &:after {
      content: '';
      position: absolute;
      display: none;
    }
  }

  &:hover input ~ &__custom {
    background-color: $color-white;
    outline: 1px $color-brand solid;
  }

  & input:checked ~ &__custom {
    background-color: $color-brand;
  }

  & input:checked ~ &__custom:after {
    display: block;
    left: 7px;
    top: 2px;
    width: 5px;
    height: 10px;
    border: solid white;
    border-width: 0 2px 2px 0;
    transform: rotate(45deg);
  }
}
</style>
