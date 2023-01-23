<template>
    <div>
        <div class="product">
            <a href="#">
                <img :src="img" :alt="title" class="product-img">
            </a>
            <a href="#" class="product-name">{{title}}</a>
            <span class="product-price">£{{price}}</span>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    img: {
        type: String,
        required: true
    },
    title: {
        type: String,
        required: true
    },
    price: {
        type: Number,
        required: true
    }
})
</script>

<style lang="scss">
.product {
    &-img {
       display: block;
       margin-bottom: 24px;
    }
    &-name {
        display: block;
        color: var(--black);
        font-size: 24px;
        line-height: 20px;
        font-family: var(--clash);
        margin-bottom: 8px;
        text-decoration: none;
        &:hover {
            text-decoration: underline;
        }
    }
    &-price {
        display: block;
        font-size: 18px;
        color: var(--black);
    }
}
</style>