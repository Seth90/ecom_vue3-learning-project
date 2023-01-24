<template>
    <div class="hero-info" :style="{ backgroundColor: background }">
        <div class="hero-info-text">
            <h2 :style="{ color: colorTitle }" class="hero-info__title">{{ title }}</h2>
            <span :style="{ color: colorDescription }" class="hero-info__description">{{ description }}</span>
        </div>
        <uiButton :color="colorLink || 'secondary'" type="link" to="/">
            View collection
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
        &__title {
            font-family: var(--clash);
            font-weight: 400;
            font-size: 32px;
            line-height: 1.5;
            margin: 0 0 20px;
        }

        &-description {
            color: var(--lightGray);
            font-family: var(--satoshi);
            font-weight: 400;
            font-size: 18px;
        }
    }
}
</style>