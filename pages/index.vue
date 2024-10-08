<template>
  <div>
    <h1 class="text-4xl font-bold mb-8">{{ $t('welcome') }}</h1>
    <h2 class="text-2xl font-semibold mb-4">{{ $t('featured') }}</h2>
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      <ProductCard v-for="product in featuredProducts" :key="product.id" :product="product" />
    </div>
  </div>
</template>

<script setup>
const featuredProducts = [
  { id: 1, name: 'Air Jordan 1', price: 220, image: 'https://via.placeholder.com/300x300' },
  { id: 2, name: 'Yeezy Boost 350', price: 300, image: 'https://via.placeholder.com/300x300' },
  { id: 3, name: 'Nike Dunk Low', price: 180, image: 'https://via.placeholder.com/300x300' },
]
</script>