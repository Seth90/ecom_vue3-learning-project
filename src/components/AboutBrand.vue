<template>
    <div class="about-brand">
        <h3 class="about-brand__title">What makes our brand different</h3>
        <div class="about-brand-elements">
            <div class="about-brand-element" v-for="(element, i) of aboutBrands" :key="i">
                <img :src="element.img" :alt="element.title" class="about-brand-element__img">
                <h4 class="about-brand-element__title">{{ element.title }}</h4>
                <span class="about-brand-element__description">{{ element.description }}</span>
            </div>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'
const aboutBrands = [
    {
        img: '/svg/Delivery.svg',
        title: 'Next day as standard',
        description: 'Order before 3pm and get your order the next day as standard'
    },
    {
        img: '/svg/Checkmark.svg',
        title: 'Made by true artisans',
        description: 'Handmade crafted goods made with real passion and craftmanship'
    },
    {
        img: '/svg/Purchase.svg',
        title: 'Unbeatable prices',
        description: 'For our materials and quality you won’t find better prices anywhere'
    },
    {
        img: '/svg/Sprout.svg',
        title: 'Recycled packaging',
        description: 'We use 100% recycled to ensure our footprint is more manageable'
    }
]
</script>

<style lang="scss" scoped>
.about-brand {
    padding: 88px 80px 130px 80px;

    @media screen and (max-width: 767px) {
        padding: 48px 24px;
    }

    &__title {
        text-align: center;
        font-size: 24px;
        color: var(--dark-primary);
        margin: 0 0 84px 0;
        font-family: var(--clash);
        font-weight: 400;

        @media screen and (max-width: 767px) {
            text-align: left;
            font-size: 20px;
            margin-bottom: 36px;
        }
    }

    &-elements {
        display: grid;
        //grid-template-columns: repeat(4, 210px);
        grid-template-columns: repeat(4, 1fr);
        grid-column-gap: 22px;
        justify-content: space-between;

        @media screen and (max-width: 1024px) {
            grid-template-columns: repeat(2, 1fr);
            gap: 20px;
        }
        @media screen and (max-width: 767px) {
            grid-template-columns: repeat(1, 1fr);
        }
    }

    &-element {
        color: var(--dark-primary);
        background: var(--lightGray);
        padding: 48px;
        @media screen and (max-width: 767px) {
            padding: 36px 24px;
        }
        &__img {
            display: block;
            margin-bottom: 12px;
        }

        &__title {
            margin: 0 0 12px 0;
            font-size: 20px;
            font-weight: 400;
        }

        &__description {
            font-size: 16px;
            line-height: 1.5;
        }
    }
}
</style>