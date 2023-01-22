<template>
    <div class="hero-info" :style="{ backgroundColor: background }">
        <div class="hero-info-text">
            <h2 :style="{ color: colorTitle }" class="hero-info__title">{{ title }}</h2>
            <span :style="{ color: colorDescription }" class="hero-info__description">{{ description }}</span>
        </div>
        <a :href="link" class="hero-info-link" :style="{ color: colorLink }">View collection</a>
    </div>
</template>

<script setup>
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
        default: '#2A254B'
    },
    background: {
        type: String,
        default: '#fff'
    }
})
</script>

<style lang="scss">
.hero {
    &-info {
        background: #fff;
        max-width: 630px;
        padding: 50px 55px;
        min-height: 444px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;

        &__title {
            font-family: 'Clash Display', sans-serif;
            font-weight: 400;
            font-size: 32px;
            line-height: 1.5;
            margin: 0 0 20px;
        }

        &-description {
            color: #5B5676;
            font-family: 'Satoshi', sans-serif;
            font-weight: 400;
            font-size: 18px;
        }

        &-link {
            color: #2A254B;
            text-decoration: none;
            width: 170px;
            height: 56px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: rgba(249, 249, 249, 0.15);
            transition: 0.3s;
            cursor: pointer;
            &:hover {
                background: rgba(249, 249, 249, 0.30);
            }
        }
    }
}
</style>