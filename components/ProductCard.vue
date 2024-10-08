<template>
  <div class="bg-white shadow-md rounded-lg overflow-hidden">
    <NuxtLink :to="`/product/${product.id}`">
      <img :src="product.image" :alt="product.name" class="w-full h-48 object-cover">
      <div class="p-4">
        <h3 class="text-lg font-semibold mb-2">{{ product.name }}</h3>
        <p class="text-gray-600">${{ product.price }}</p>
      </div>
    </NuxtLink>
    <div class="px-4 pb-4">
      <button @click="$emit('addToCart', product)" class="w-full bg-green-500 text-white px-4 py-2 rounded hover:bg-green-600 transition">
        {{ $t('addToCart') }}
      </button>
    </div>
  </div>
</template>

<script setup>
defineProps({
  product: {
    type: Object,
    required: true,
  },
})
defineEmits(['addToCart'])
</script>