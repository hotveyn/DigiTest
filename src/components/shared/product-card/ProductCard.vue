<script setup lang="ts">
import IconBox from '@/components/shared/icon/IconBox.vue'
import IconBoxBig from '@/components/shared/icon/IconBoxBig.vue'
import IconFire from '@/components/shared/icon/IconFire.vue'
import BaseLabel from '@/components/shared/label/BaseLabel.vue'
import BaseButton from '@/components/shared/button/BaseButton.vue'
interface IProductCard {
  brand: string
  price: number
  oldPrice: number
  discount: number
  outofstock: boolean
}

defineProps<{
  productCard: IProductCard
}>()
</script>

<template>
  <div class="product-card w">
    <div class="product-card__img w">
      <IconBox v-if="!productCard.outofstock" />
      <IconBoxBig v-else />
      <div class="product-card__heat">
        <p>Хит продаж</p>
        <IconFire />
      </div>
      <BaseLabel class="product-card__discount">{{ productCard.discount + '%' }}</BaseLabel>
    </div>
    <p class="product-card__brand">Бренд</p>
    <p class="product-card__brand-description">{{ productCard.brand }}</p>
    <div v-if="!productCard.outofstock" class="product-card__prices">
      <span class="product-card__price_current">{{ productCard.price + ' ₽' }}</span>
      <span class="product-card__price_old">{{ productCard.oldPrice + ' ₽' }}</span>
    </div>
    <BaseButton v-if="!productCard.outofstock" class="product-card__buy" type="flat"
      >Купить</BaseButton
    >
    <BaseButton v-else class="product-card__buy product-card__buy_invalid" type="invalid"
      >Сообщить о поступлении</BaseButton
    >
  </div>
</template>

<style scoped lang="scss">
.product-card {
  max-width: 333px;
  cursor: pointer;

  &:hover &__brand-description {
    color: $color-font-hover;
  }

  &__img {
    position: relative;
    background-color: #f8f8fa;
    @include flex();
    height: 200px;
  }

  &__heat {
    @include flex();
    position: absolute;
    border: 1px solid $color-scroll;
    border: 4px;
    top: 12px;
    left: 12px;
    padding: 8px;
    background-color: $color-white;
    font-size: 14px;
    color: $color-font;
  }

  &__discount {
    position: absolute;
    bottom: 12px;
    left: 12px;
  }

  &__brand {
    font-size: 14px;
    margin-top: 16px;
    color: $color-font-second;
  }

  &__brand-description {
    font-size: 14px;
    margin-top: 8px;
    color: $color-font;
    transition: color 0.2s;
  }

  &__prices {
    margin-top: 16px;
    @include flex(start);
    gap: 8px;
  }
  &__price {
    &_current {
      font-size: 16px;
      color: $color-font;
      font-weight: 700;
    }
    &_old {
      color: $color-font-second;
      font-size: 12px;
      font-weight: 400;
      text-decoration: line-through;
    }
  }

  &__buy {
    margin-top: 16px;

    &_invalid {
      margin-top: 62px;
    }
  }
}
</style>
