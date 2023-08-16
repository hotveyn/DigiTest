<script setup lang="ts"></script>

<template>
  <div class="label">
    <p class="label__text"><slot /></p>
  </div>
</template>

<style scoped lang="scss">
.label {
  border-radius: 4px;
  padding: 6px 10px;
  height: 26px;
  width: fit-content;
  @include flex();
  background-color: $color-brand;
  &__text {
    color: $color-white;
    font-size: 14px;
    font-style: normal;
    font-weight: 700;
  }
}
</style>
