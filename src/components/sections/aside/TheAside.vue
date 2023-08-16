<script setup lang="ts">
import BaseCategory from '@/components/shared/category/BaseCategory.vue'
import BaseInput from '@/components/shared/input/BaseInput.vue'
import IconGlassSecondary from '@/components/shared/icon/IconGlassSecondary.vue'
import BaseCheckbox from '@/components/shared/checkbox/BaseCheckbox.vue'
</script>

<template>
  <aside class="aside">
    <div class="aside__content">
      <div class="aside__categories">
        <BaseCategory type="parent">
          <template #name>Название категории</template>
          <template #count>3</template>
        </BaseCategory>
        <BaseCategory type="child">
          <template #name>Название категории</template>
          <template #count>3</template>
        </BaseCategory>
        <BaseCategory type="child">
          <template #name>Название категории</template>
          <template #count>3</template>
        </BaseCategory>
        <BaseCategory type="child" active>
          <template #name>Название категории</template>
          <template #count>3</template>
        </BaseCategory>
      </div>
      <div class="aside__price">
        <p class="aside__title">Цена</p>
        <div class="aside__group aside__group_price">
          <BaseInput type="number">
            <template #left> от </template>
          </BaseInput>
          <span class="aside__divider" />
          <BaseInput type="number">
            <template #left> от </template>
          </BaseInput>
        </div>
      </div>
      <div class="aside__brand">
        <div class="aside__header">
          <p class="aside__title">Бренд</p>
          <a class="aside__clear">Очистить</a>
        </div>
        <BaseInput placeholder="Поиск" class="aside__search" type="text">
          <template #left> <IconGlassSecondary /> </template>
        </BaseInput>
        <div class="aside__group aside__group_brand">
          <BaseCheckbox>
            <template #left> Атрибут </template>
            <template #count> 3 </template>
          </BaseCheckbox>
          <BaseCheckbox>
            <template #left> Атрибут </template>
            <template #count> 3 </template>
          </BaseCheckbox>
          <BaseCheckbox>
            <template #left> Атрибут </template>
            <template #count> 3 </template>
          </BaseCheckbox>
          <BaseCheckbox>
            <template #left> Атрибут </template>
            <template #count> 3 </template>
          </BaseCheckbox>
          <BaseCheckbox>
            <template #left> Атрибут </template>
            <template #count> 3 </template>
          </BaseCheckbox>
          <BaseCheckbox>
            <template #left> Атрибут </template>
            <template #count> 3 </template>
          </BaseCheckbox>
          <BaseCheckbox>
            <template #left> Атрибут </template>
            <template #count> 3 </template>
          </BaseCheckbox>
        </div>
      </div>
      <div class="aside__size">
        <p class="aside__title">Размер</p>
        <div class="aside__group aside__group_size">
          <BaseCheckbox>
            <template #left> Атрибут </template>
            <template #count> 3 </template>
          </BaseCheckbox>
          <BaseCheckbox>
            <template #left> Атрибут </template>
            <template #count> 3 </template>
          </BaseCheckbox>
          <BaseCheckbox>
            <template #left> Атрибут </template>
            <template #count> 3 </template>
          </BaseCheckbox>
          <BaseCheckbox>
            <template #left> Атрибут </template>
            <template #count> 3 </template>
          </BaseCheckbox>
          <BaseCheckbox>
            <template #left> Атрибут </template>
            <template #count> 3 </template>
          </BaseCheckbox>
          <BaseCheckbox>
            <template #left> Атрибут </template>
            <template #count> 3 </template>
          </BaseCheckbox>
        </div>
      </div>
    </div>
    <aside class="aside_mob">
      <h2>Название категории</h2>
    </aside>
  </aside>
</template>

<style scoped lang="scss">
.aside {
  &__content {
    @include flex($ai: unset, $fd: column);
    gap: 28px;
  }

  &__title {
    text-align: center;
    font-size: 16px;
    font-style: normal;
    font-weight: 700;
    line-height: 20px $color-font;
  }

  &__header {
    @include flex(space-between);
  }

  &__clear {
    cursor: pointer;
    color: $color-font-second;
    font-size: 12px;
    font-weight: 400;
    line-height: 12px; /* 100% */
    text-decoration-line: underline;
  }

  &__group {
    margin-top: 16px;

    &_price {
      display: grid;
      grid-template-columns: 1fr 10px 1fr;
      align-items: center;
      gap: 16px;
    }

    &_brand {
      padding: 1px;
      display: grid;
      grid-template-columns: 1fr;
      gap: 16px;
      max-height: 180px;
      overflow-y: scroll;

      &::-webkit-scrollbar {
        width: 3px;
      }

      &::-webkit-scrollbar-track {
        background-color: rgba(0, 0, 0, 0);
      }

      &::-webkit-scrollbar-thumb {
        box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.3);
      }
    }

    &_size {
      display: grid;
      grid-template-columns: 1fr;
      gap: 16px;
    }
  }

  &__search {
    margin-top: 16px;
  }

  &__divider {
    height: 1px;
    width: 10px;
    display: block;
    background-color: $color-border;
  }
}

@media (width >= 950px) {
  .aside_mob {
    display: none;
  }
}

@media (width < 950px) {
  .aside {
    &__content {
      display: none;
    }

    &_mob {
      display: block;

      h1 {
        color: $color-font;
        font-size: 22px;
        line-height: 28px; /* 127.273% */
      }
    }
  }
}
</style>
