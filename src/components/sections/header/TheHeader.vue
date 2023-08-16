<script setup lang="ts">
import BaseLogo from '@/components/shared/logo/BaseLogo.vue'
import BaseButton from '@/components/shared/button/BaseButton.vue'
import SearchBar from '@/components/shared/search-bar/SearchBar.vue'
import BaseInput from '@/components/shared/input/BaseInput.vue'
import IconBack from '@/components/shared/icon/IconBack.vue'
</script>

<template>
  <header class="header w">
    <div class="container header__content">
      <div class="header__left">
        <BaseLogo />
        <BaseButton type="primary"> Каталог </BaseButton>
      </div>
      <SearchBar class="header__search-bar" />
      <div class="header__links">
        <a href="#" class="header__link">Информация о компании</a>
        <a href="#" class="header__link">Контакты</a>
        <a href="#" class="header__link">Полезные ссылки</a>
      </div>
    </div>
    <div class="header_mob container">
      <IconBack />
      <BaseInput type="secondary" />
    </div>
  </header>
</template>

<style scoped lang="scss">
.header {
  padding: 12px 0;

  &__content {
    display: grid;
    grid-template-columns: 257px auto 400px;
    gap: 24px;
  }

  &__left {
    @include flex();
    gap: 6px;
  }

  &__links {
    align-self: center;
    @include flex();
    gap: 20px;
  }

  &__link {
    color: $color-font;
    text-wrap: nowrap;
  }
}

@media (width >= 950px) {
  .header_mob {
    display: none;
  }
}

@media (width < 950px) {
  .header__content {
    display: none;
  }
  .header_mob {
    height: 45px;
    @include flex();
    gap: 16px;
  }
}
</style>
