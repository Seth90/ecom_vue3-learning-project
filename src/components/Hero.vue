<template>
    <div class="hero">
        <HeroInformation 
            title="Luxury homeware for people who love timeless design quality"
            description="Shop the new Spring 2022 collection today" 
            link="#"
            colorLink="lightgray" />
    </div>
</template>

<script setup>
import HeroInformation from '@/Components/HeroInformation.vue';
</script>

<style lang="scss" scoped>
.hero {
    background: url('/imgs/hero.jpg');
    height: 704px;
    background-size: auto;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    padding-right: 80px;
    &-img {
        max-width: 100%;
    }
}
</style>