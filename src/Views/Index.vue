<template>
    <div class="container">
        <Hero />
        <AboutBrand />
        <Products :products="popularProducts"  />
        <Ideas/>
        <Subscribe />
    </div>
</template>

<script setup>
import { onMounted, ref } from 'vue';
import api from '@/api';

import Hero from '@/components/Hero.vue';
import AboutBrand from '@/components/AboutBrand.vue';
import Products from '@/components/Products4Column.vue';
import Ideas from '@/components/Ideas.vue';
import Subscribe from '@/components/Subscribe.vue';

const popularProducts = ref([]);

onMounted(async () => {
    popularProducts.value = await api.getPopularProducts();
})
</script>

<style lang="scss">
</style>