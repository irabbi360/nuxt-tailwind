<template>
  <div>
    <div class="grid grid-cols-4 gap-5">
      <div
        v-for="p in products"
        class="flex flex-col shadow-md bg-white p-6 rounded-md"
        >
        <ProductCard :product="p" />
      </div>
    </div>
  </div>
</template>

<script setup>
  //  fetch the products
  const { data: products } = await useFetch('https://fakestoreapi.com/products')

  definePageMeta({
    layout: "products",
  })

  useHead({
    title: 'Nuxt Tailwind | Merch',
    meta: [
      { name: 'description', content: 'Nuxt 3 Merch'}
    ]
  })
</script>