<script setup>

const { product } = defineProps(['product'])
</script>

<template>
    
    <div class="p-4 rounded-md bg-white shadow-md h-full text-center">
        <img :src="`${product.image}`" class="thumb" />
        <p class="font-bold text-gray-500 m-4 truncate">{{ product.title }}</p>
        <NuxtLink :to="`/products/${product.id}`">
            <p class="btn my-4">View Details</p>
        </NuxtLink>
    </div>
</template>

<style  scoped>
.thumb {
    max-height: 120px;
    max-width: 70%;
    margin: 0 auto;
  }
</style>