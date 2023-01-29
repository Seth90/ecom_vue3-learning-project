<template>
    <div class="hero">
        <HeroInformation 
            title="Luxury homeware for people who love timeless design quality"
            description="Shop the new Spring 2022 collection today" 
            link="#"
            colorLink="lightgray" />
        <img src="/imgs/hero.jpg" alt="hero" class="hero__image">
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
    @media screen and (max-width: 767px) {
        height: auto;
        background: transparent;
        padding-right: 0;
        display: block;
    }
    &__image {
        width: 100%;
        height: 100%;
        }
    &-img {
        max-width: 100%;
    }
}
</style>