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
            <div class="product-block">
                <span class="product-block__title">Dimensions</span>
                <span class="product-param" v-for="(param, i) of product.params" :key="i">{{ param.title }}: {{ param.value
                }}</span>
            </div>
            <div class="product-block">
                <span class="product-block__title">Quantity</span>
                <div class="product-quantity">
                    <span class="product-quantity-symbol" @click="changeQuantity('minus')">-</span>
                    <span class="product-quantity-value">{{ quantity }}</span>
                    <span class="product-quantity-symbol" @click="changeQuantity('plus')">+</span>
                </div>
            </div>
            <Button text="Add to cart" color="primary" @click="cartStore.addToCart(product, quantity)"></Button>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue';
import Button from '@/components/UI/Button.vue';
import {useCartStore} from '@/store/cart.js'
const props = defineProps({
    product: {
        type: Object,
        default: () => { },
        requred: true
    }
});

const cartStore = useCartStore();
const quantity = ref(1);

const changeQuantity = (type) => {
    if (type === 'minus') {
        quantity.value === 1 ? quantity.value = 1 : quantity.value--;
    }
    if (type === 'plus') {
        quantity.value === 3 ? quantity.value = 3 : quantity.value++;
    }
}
const addToCart = () => {
    
}
</script>

<style lang="scss" scoped>
.product {
    background: var(--lightGray);
    padding: 50px 80px;
    display: grid;
    align-items: center;
    grid-template-columns: 1fr 1fr;
    column-gap: 35px;
    margin-bottom: 65px;
    img {
        max-width: 600px;
    }
    &-name {
        margin: 0 0 16px 0;
        font-family: var(--clash);
        font-size: 36px;
        font-weight: 400;
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

    &-param {
        display: block;
    }

    &-quantity {
        background: #fff;
        width: 122px;
        height: 46px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 0 16px;

        &-symbol {
            color: var(--border-gray);
            cursor: pointer;
        }
    }
}
</style>