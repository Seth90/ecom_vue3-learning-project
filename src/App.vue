<template>
    <div class="container">
        <Header />
        <Hero />
        <AboutBrand />
        <Products4Column />
        <Ideas/>
    </div>
</template>

<script setup>
import Header from '@/components/Layout/Header.vue'
import Hero from '@/components/Hero.vue'
import AboutBrand from '@/components/AboutBrand.vue'
import Products4Column from '@/components/Products4Column.vue'
import Ideas from '@/components/Ideas.vue'


</script>

<style lang="scss">
@import '@/assets/styles/global.scss';
</style>
