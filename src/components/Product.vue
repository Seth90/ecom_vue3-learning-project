<template>
    <div>
        <div class="product">
            <router-link :to="`products/${id}`">
                <img :src="img" :alt="title" class="product-img">
            </router-link>
            <router-link :to="`products/${id}`" class="product-name">{{title}}</router-link>
            <span class="product-price">£{{price}}</span>
        </div>
    </div>
</template>

<script setup>
const props = defineProps({
    id: {
        type: String,
        required: true
    },
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

<style lang="scss" scoped>
.product {
    &-img {
       display: block;
       width: 100%;
       margin-bottom: 24px;
       object-fit: cover;
    }
    &-name {
        display: block;
        color: var(--dark-primary);
        font-size: 20px;
        //line-height: 1.4;
        font-family: var(--clash);
        margin-bottom: 8px;
        text-decoration: none;
        @media screen and (max-width: 767px) {
            font-size: 16px;
        }
        &:hover {
            text-decoration: underline;
        }
    }
    &-price {
        display: block;
        font-size: 18px;
        color: var(--dark-primary);
    }
}
</style>