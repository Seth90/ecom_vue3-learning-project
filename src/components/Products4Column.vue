<template>
    <div class="products-container">
        <div class="products">
            <Product v-for="product of products"
            :id="product.id"
            :key="product.id" 
            :img="product.img" 
            :title="product.title"
            :price="product.price" />
        </div>
        <div class="products-link">
            <uiButton :mobileFullWidth="true" color="lightgray" type="link" to="/" text="View collection">s
            </uiButton>
        </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'
import Product from '@/components/Product.vue'
import uiButton from '@/components/UI/Button.vue'

const props = defineProps({
    products: {
        required: true,
    }
})

</script>

<style lang="scss" scoped>
.products {
    padding: 0 80px;
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    grid-column-gap: 20px;
    margin-bottom: 64px;

    @media screen and (max-width: 1024px) {
        grid-template-columns: repeat(2, 1fr);
        row-gap: 20px;
    }

    @media screen and (max-width: 767px) {
        grid-template-columns: repeat(2, 1fr);
        row-gap: 20px;
        padding: 0 24px;
        margin-bottom: 45px;
    }

    &-container {
        margin-bottom: 56px;

        @media screen and (max-width: 767px) {
            margin-bottom: 0px;
        }
    }

    &-link {
        text-align: center;

        @media screen and (max-width: 767px) {
            padding: 40px 25px 28px 24px;
        }

        &:hover {
            text-decoration: underline;
        }
    }
}
</style>