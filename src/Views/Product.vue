<template>
    <div>
        <ProductDetail :product="currentProduct"/>
    </div>
</template>

<script setup>
import {ref, onMounted} from 'vue';
import { useRoute, useRouter } from 'vue-router';
import api from '@/api.js'
import ProductDetail from '../components/ProductDetail.vue';

const route = useRoute();
const router = useRouter();
const productId = ref('');
var currentProduct = ref({});

onMounted(async () => {
    productId.value = route.params.id;
    currentProduct = await api.getProduct(productId.value);
})
</script>

<style lang="">
    
</style>