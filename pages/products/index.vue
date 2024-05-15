<template>
    <div>
      <select v-model="selectedCategory" @change="logSelectedCategory" class="w-full bg-white rounded-md px-3 py-3 text-sm border-gray-300 border transition-colors placeholder:text-muted-foreground focus:right-0 focus-visible:ring-0 focus-visible:ring-offset-0 focus-visible:border-gray-400 mb-6">
        <option value="">All Categories</option>
        <option v-for="category in categories" :value="category">{{ category }}</option>
      </select>
  
      <Swiper :loop="true" :breakpoints="swiperOptions.breakpoints">
        <SwiperSlide v-for="product in filteredProducts" :key="product.id">
          <!-- Display product details -->
          <ProductCard :product="product" />
        </SwiperSlide>
      </Swiper>
    </div>
  </template>
  
<script setup>
    import { ref, computed } from 'vue';
    import ProductCard from '~/components/ProductCard.vue';
    definePageMeta({
        layout:'products'
    })
  
    // categories
    const { data: categories } = await useFetch('https://fakestoreapi.com/products/categories');
  
    // products
    const { data: allProducts } = await useFetch('https://fakestoreapi.com/products');
  
    const selectedCategory = ref('');
  
    const filteredProducts = computed(() => {
        if (!selectedCategory.value) {
        return allProducts.value; 
        } else {
        return allProducts.value.filter(product =>
            product.category === selectedCategory.value
        );
        }
    });
  
    //swiper options for responsive layout
        const swiperOptions = {
            breakpoints: {
                320: {
                slidesPerView: 1,
                spaceBetween: 10
                },
                480: {
                slidesPerView: 2,
                spaceBetween: 10
                },
                768: {
                slidesPerView: 3,
                spaceBetween: 20
                },
                1024: {
                slidesPerView: 4,
                spaceBetween: 20
                }
            }
        };
</script>
  