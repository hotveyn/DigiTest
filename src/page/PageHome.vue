<script setup lang="ts">
import ProductCard from '@/components/shared/product-card/ProductCard.vue'
const productCards = [
  {
    brand: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    price: 5990,
    oldPrice: 5990,
    discount: 25,
    outofstock: false
  },
  {
    brand: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    price: 5990,
    oldPrice: 5990,
    discount: 25,
    outofstock: false
  },
  {
    brand: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    price: 5990,
    oldPrice: 5990,
    discount: 25,
    outofstock: true
  },
  {
    brand: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    price: 5990,
    oldPrice: 5990,
    discount: 25,
    outofstock: false
  },
  {
    brand: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    price: 5990,
    oldPrice: 5990,
    discount: 25,
    outofstock: false
  },
  {
    brand: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    price: 5990,
    oldPrice: 5990,
    discount: 25,
    outofstock: false
  },
  {
    brand: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    price: 5990,
    oldPrice: 5990,
    discount: 25,
    outofstock: false
  },
  {
    brand: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    price: 5990,
    oldPrice: 5990,
    discount: 25,
    outofstock: false
  },
  {
    brand: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    price: 5990,
    oldPrice: 5990,
    discount: 25,
    outofstock: false
  },
  {
    brand: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    price: 5990,
    oldPrice: 5990,
    discount: 25,
    outofstock: false
  },
  {
    brand: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    price: 5990,
    oldPrice: 5990,
    discount: 25,
    outofstock: false
  },
  {
    brand: 'Полное название товара в несколько строк для вида с обрывом в конце...',
    price: 5990,
    oldPrice: 5990,
    discount: 25,
    outofstock: false
  }
]
</script>

<template>
  <div class="page-home">
    <div class="page-home__cards">
      <ProductCard
        v-for="(productCard, index) in productCards"
        :key="index"
        :product-card="productCard"
      />
    </div>
  </div>
</template>

<style scoped lang="scss">
.page-home {
  container: page-home / inline-size;
  &__cards {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 24px;
  }
}

@container page-home (max-width: 900px) {
  .page-home {
    &__cards {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 24px;
    }
  }
}

@container page-home (max-width: 600px) {
  .page-home {
    &__cards {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 24px;
    }
  }
}
</style>
