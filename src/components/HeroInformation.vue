<template>
    <div class="hero-info" :style="{ backgroundColor: background }">
        <div class="hero-info-text">
            <h2 :style="{ color: colorTitle }" class="hero-info__title">{{ title }}</h2>
            <span :style="{ color: colorDescription }" class="hero-info__description">{{ description }}</span>
        </div>
        <uiButton :mobileFullWidth="true" :color="colorLink || 'secondary'" type="link" text="View collection" to="/">
        </uiButton>

        <!-- <a :href="link" class="hero-info-link" :style="{ color: colorLink }">View collection</a> -->
    </div>
</template>

<script setup>
import uiButton from '@/components/UI/Button.vue'
const props = defineProps({
    title: {
        type: String,
        required: false
    },
    description: {
        type: String,
        required: false
    },
    link: {
        type: String,
        required: false
    },
    colorTitle: {
        type: String,
        default: ''
    },
    colorDescription: {
        type: String,
        default: '#5b5676'
    },
    colorLink: {
        type: String,
        //default: '#2a254b'
        required: false
    },
    background: {
        type: String,
        default: '#fff'
    }
})
</script>

<style lang="scss" scoped>
.hero {
    &-info {
        background: #fff;
        max-width: 630px;
        padding: 50px 55px;
        min-height: 444px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: flex-start;

        @media screen and (max-width: 767px) {
            padding: 47px 24px 32px 24px;
            min-height: 0;
        }

        &-text {
            @media screen and (max-width: 767px) {
                margin-bottom: 32px;
            }
        }

        &__title {
            font-family: var(--clash);
            font-weight: 400;
            font-size: 32px;
            //line-height: 1.5;
            margin: 0 0 20px;

            @media screen and (max-width: 767px) {
                font-size: 20px;
            }
        }

        &__description {
            color: var(--lightGray);
            font-family: var(--satoshi);
            font-weight: 400;
            font-size: 18px;

            @media screen and (max-width: 767px) {
                font-size: 14px;
            }
        }
    }
}
</style>