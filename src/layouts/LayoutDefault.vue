<script setup lang="ts">
import TheHeader from '@/components/sections/header/TheHeader.vue'
import TheAside from '@/components/sections/aside/TheAside.vue'
</script>

<template>
  <div class="layout-default">
    <TheHeader />
    <main class="main">
      <div class="container main__content">
        <TheAside />
        <div class="main__slotted">
          <slot />
        </div>
      </div>
    </main>
  </div>
</template>

<style scoped lang="scss">
.layout-default {
  display: flex;
  flex-direction: column;
  gap: 24px;
}
.main {
  &__content {
    display: grid;
    grid-template-columns: 280px auto;
    align-items: start;
    gap: 36px;
  }
}
@media (width < 950px) {
  .main {
    &__content {
      display: grid;
      grid-template-columns: 1fr;
      align-items: start;
      gap: 36px;
    }
  }
}
</style>
