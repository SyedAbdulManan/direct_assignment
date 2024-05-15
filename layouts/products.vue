<template>
    <div>
        <header class="app-header shadow-sm bg-white">
            <nav class="container mx-auto flex p-4 justify-between">
                <NuxtLink to="/" class="font-bold">Fe Assignment</NuxtLink>
                <ul class="flex gap-4">
                    <li><NuxtLink to="/">Home</NuxtLink></li>
                    <li><NuxtLink to="/about">About</NuxtLink></li>
                    <li><NuxtLink to="/Products">Product</NuxtLink></li>
                </ul>
            </nav>
        </header>
        <div class="app-content container mx-auto p-4">
            <slot/>
        </div>
        <footer class="app-footer bg-white text-center p-3">
            I am the app footer
        </footer>
    </div>
</template>
<style scoped>
.router-link-exact-active{
    color: #12b488;
    font-weight: 600;
}
</style>