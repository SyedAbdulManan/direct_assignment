<script setup lang="ts">

</script>

<template>
    <div class="h-[480px] flex flex-col justify-center home-banner bg-cover">
        <div class="container mx-auto">
            <div class="grid md:grid-cols-3">
                <div>
                    <h1 class="text-gray-100 font-bold text-[36px] ">We Provide Excellence</h1>
                    <p class="text-gray-100 italic text-[18px]">"When everything feels like an uphill struggle, think about the view from the top"</p>
                    <NuxtLink to="/products">
                        <p class="btn my-4">Shop Now</p>
                    </NuxtLink>
                </div>
            </div>
        </div>
    </div>
</template>

<style lang="scss" scoped>
.home-banner{
    background-image: url(../assets/images/backgrounds/home-banner.png);
}
</style>