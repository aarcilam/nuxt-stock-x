<template>
  <div class="container mx-auto px-4 py-8">
    <div class="flex flex-wrap -mx-4">
      <div class="w-full md:w-1/2 px-4 mb-8 md:mb-0">
        <img :src="product.image" :alt="product.name" class="w-full rounded-lg shadow-lg">
      </div>
      <div class="w-full md:w-1/2 px-4">
        <h1 class="text-3xl font-bold mb-4">{{ product.name }}</h1>
        <p class="text-xl mb-4">{{ t('currentPrice') }}: ${{ product.price }}</p>
        <p class="text-gray-600 mb-6">{{ product.description }}</p>
        
        <div class="mb-6">
          <h2 class="text-xl font-semibold mb-2">{{ t('makeBid') }}</h2>
          <div class="flex items-center">
            <input v-model="bidAmount" type="number" class="border rounded-l px-4 py-2 w-32" :placeholder="t('enterBid')">
            <button @click="placeBid" class="bg-blue-500 text-white px-4 py-2 rounded-r hover:bg-blue-600 transition">{{ t('bid') }}</button>
          </div>
        </div>
        
        <button @click="buyNow" class="w-full bg-green-500 text-white px-6 py-3 rounded-lg text-lg font-semibold hover:bg-green-600 transition">
          {{ t('buyNow') }}
        </button>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import { useRoute } from 'vue-router'
import { useI18n } from 'vue-i18n'

const route = useRoute()
const { t } = useI18n()

const productId = route.params.id

// Simulated product data (replace with actual data fetching in a real app)
const product = ref({
  id: productId,
  name: 'Air Jordan 1 Retro High',
  price: 220,
  image: 'https://via.placeholder.com/500x500',
  description: 'The Air Jordan 1 Retro High offers a clean, classic look that\'s comfortable and stylish.'
})

const bidAmount = ref('')

const placeBid = () => {
  if (bidAmount.value && Number(bidAmount.value) > 0) {
    alert(`${t('bidPlaced')}: $${bidAmount.value}`)
    bidAmount.value = ''
  } else {
    alert(t('invalidBid'))
  }
}

const buyNow = () => {
  alert(`${t('purchaseConfirmation')}: ${product.value.name} ${t('for')} $${product.value.price}`)
}
</script>