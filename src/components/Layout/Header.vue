<template>
    <header class="header">
        <div class="header-top">
            <div class="header-top-left">
                <div class="header-top-search">
                    <img src="/svg/header-search.svg" alt="Search" class="header-top__icon">
                </div>
                <div class="header-top-mobile-menu" @click="isOpenedMobileMenu = !isOpenedMobileMenu">
                    <img src="/svg/Menu.svg" alt="Menu" class="header-top__icon">
                </div>
            </div>

            <router-link to="/" class="header-logo">Avion</router-link>
            <div class="header-top-right">
                <div href="#" class="header-top-right__cart">
                    <router-link to="/cart">
                        <img src="/svg/header-cart.svg" alt="cart">
                    </router-link>
                    <span class="header-top-right__count" v-if="cartStore.cart.length">{{ cartStore.cart.length }}</span>
                </div>
                <div href="#" class="header-top-righh__user">
                    <router-link to="/user">
                        <img src="/svg/header-user.svg" alt="user">
                    </router-link>
                </div>
            </div>
        </div>
        <div class="header-menu">
            <router-link class="header-menu__link" to="element.path" v-for="(element, i) of menu" :key="i">{{
                element.name
            }}</router-link>
        </div>
        <div class="header-menu-mobile" v-if="isOpenedMobileMenu">

            <router-link class="header-menu-mobile__link" to="element.path" v-for="(element, i) of menu" :key="i">{{
                element.name
            }}</router-link>
        </div>
    </header>
</template>

<script setup>
import { ref } from 'vue';
import {useCartStore} from '@/store/cart.js';
const cartStore = useCartStore();


const menu = [
    {
        name: 'Plant pots',
        path: '/plants'
    },
    {
        name: 'Ceramics',
        path: '/ceramics'
    },
    {
        name: 'Tables',
        path: '/tables'
    }
]
const isOpenedMobileMenu = ref(false);
</script>

<style lang="scss" scoped>
.header {
    height: 132px;
    background: white;
    position: relative;
    @media screen and (max-width: 767px) {
        height: auto;
        padding: 20px 20px 27px 24px;
    }

    &-top {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        justify-content: space-between;
        height: 70px;
        align-items: center;
        border-bottom: 1px solid rgba($color: #000000, $alpha: 0.1);
        margin: 0 28px;

        @media screen and (max-width: 767px) {
            margin: 0;
            border: none;
            height: auto;
            display: flex;
            justify-content: space-between;
        }
        &__icon {
            display: block;
        }
        &-left {
            display: flex;
            align-items: center;
            @media screen and (max-width: 767px) {
                order: 2;
            }
        }
        &-mobile-menu {
            margin-left: 16px;
            display: none;
            @media screen and (max-width: 767px) {
                display: block;
            }
        }
        &-search {
            
        }

        &-right {
            display: flex;
            align-items: center;
            justify-content: flex-end;

            @media screen and (max-width: 767px) {
                display: none;
            }

            &__cart {
                margin-right: 16px;
                position: relative;
            }
            &__count {
                position: absolute;
                width: 15px;
                height: 15px;
                background: var(--primary);
                border-radius: 50%;
                text-decoration: none;
                color: #fff;
                font-size: 10px;
                display: flex;
                justify-content: center;
                align-items: center;
                bottom: 0;
                left: 50%;
            }
        }
    }

    &-logo {
        color: #22202e;
        font-size: 24px;
        text-decoration: none;
        font-family: var(--clash);
        text-align: center;

        @media screen and (max-width: 767px) {
            order: 1;
        }

        &:hover {
            text-decoration: underline;
        }
    }

    &-menu {
        height: 62px;
        display: flex;
        justify-content: center;
        align-items: center;

        @media screen and (max-width: 767px) {
            display: none;
        }

        &__link {
            margin: 0 22px;
            color: #726E8D;
            text-decoration: none;

            &:hover {
                text-decoration: underline;
            }
        }
        &-mobile {
            position: absolute;
            background: #fff;
            padding: 40px 24px;
            top: 60px;
            width: 100%;
            padding: 10px;
            &-top {
                display: flex;
                justify-content: flex-end;
                margin-bottom: 24px;
            }
            &__link {
            display: block;
            margin-bottom: 20px;
            color: #726E8D;
            text-decoration: none;
            }
            &:last-child {
                margin-bottom: 0;
            }

            &:hover {
                text-decoration: underline;
            }
        }
        
    }
}
</style>