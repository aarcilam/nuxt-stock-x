<template>
  <div>
    <header class="bg-gray-800 text-white p-4">
      <nav class="container mx-auto flex justify-between items-center">
        <NuxtLink to="/" class="text-2xl font-bold">StockX Clone</NuxtLink>
        <div>
          <NuxtLink to="/products" class="mr-4">{{ $t('products') }}</NuxtLink>
          <select v-model="$i18n.locale" class="bg-gray-700 text-white p-1">
            <option value="en">English</option>
            <option value="es">Español</option>
          </select>
        </div>
      </nav>
    </header>
    <main class="container mx-auto mt-8">
      <NuxtPage />
    </main>
    <footer class="bg-gray-800 text-white p-4 mt-8">
      <div class="container mx-auto text-center">
        &copy; 2024 StockX Clone
      </div>
    </footer>
  </div>
</template>

<script setup>
import { useI18n } from 'vue-i18n'

const { t } = useI18n()
</script>