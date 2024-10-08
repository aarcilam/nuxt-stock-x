<template>
  <div>
    <h1 class="text-4xl font-bold mb-8">{{ $t('allProducts') }}</h1>
    <div class="grid grid-cols-1 md:grid-cols-4 gap-6">
      <ProductCard v-for="product in products" :key="product.id" :product="product" />
    </div>
  </div>
</template>

<script setup>
const products = [
  { id: 1, name: 'Air Jordan 1', price: 220, image: 'https://via.placeholder.com/300x300' },
  { id: 2, name: 'Yeezy Boost 350', price: 300, image: 'https://via.placeholder.com/300x300' },
  { id: 3, name: 'Nike Dunk Low', price: 180, image: 'https://via.placeholder.com/300x300' },
  { id: 4, name: 'Adidas Ultra Boost', price: 200, image: 'https://via.placeholder.com/300x300' },
  { id: 5, name: 'New Balance 990', price: 190, image: 'https://via.placeholder.com/300x300' },
  { id: 6, name: 'Converse Chuck Taylor', price: 80, image: 'https://via.placeholder.com/300x300' },
]
</script>