<template>
    <div class="product">
        <div>
            <img :src="product.image" :alt="product.name">
        </div>
        <div>
            <h2 class="product-name">{{ product.name }}</h2>
            <span class="product-price">${{ product.price }}</span>
            <div class="product-block product-description">
                <span class="product-block__title">Product description</span>
                <div v-html="product.description"></div>
            </div>
        </div>
    </div>
</template>

<script setup>
const props = defineProps ({
    product: {
        type: Object,
        default: () => {},
        requred: true
    }
})
</script>

<style lang="scss" scoped>
    .product {
        background: var(--lightGray);
        padding: 50px 80px;
        display: grid;
        align-items: center;
        grid-template-columns: 1fr 580px;
        column-gap: 35px;
        img {
            max-width: 600px;
        };
        &-name {
            margin: 0 0 16px 0;
            font-family: var(--clash);
            font-size: 36px;
        }
        &-price {
            display: block;
            font-size: 24px;
            margin-bottom: 28px;
        }
        &-block {
            margin-bottom: 40px;
            &__title {
                display: block;
                font-family: var(--clash);
                margin-bottom: 14px;
            }
        }
        &-description {
            border-top: 1px solid var(--border-gray);
            padding-top: 24px;

        }
    }
</style>