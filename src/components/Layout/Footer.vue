<template>
    <footer class="footer">
        <div class="footer-content">
            <div class="footer-top">
                <div class="footer-menu">
                    <div class="footer-menu-column">
                        <span class="footer-menu__title">Menu</span>
                        <router-link to="/" class="footer-menu__link">New arrivals</router-link>
                        <router-link to="/" class="footer-menu__link">Best sellers</router-link>
                        <router-link to="/" class="footer-menu__link">Recently viewed</router-link>
                        <router-link to="/" class="footer-menu__link">Popular this week</router-link>
                        <router-link to="/" class="footer-menu__link">All products</router-link>
                    </div>
                    <div class="footer-menu-column">
                        <span class="footer-menu__title">Categories</span>
                        <router-link to="/" class="footer-menu__link">Crockery</router-link>
                        <router-link to="/" class="footer-menu__link">Furniture</router-link>
                        <router-link to="/" class="footer-menu__link">Homeware</router-link>
                        <router-link to="/" class="footer-menu__link">Plant pots</router-link>
                        <router-link to="/" class="footer-menu__link">Chairs</router-link>
                        <router-link to="/" class="footer-menu__link">Crockery</router-link>
                    </div>
                    <div class="footer-menu-column">
                        <span class="footer-menu__title">Our company</span>
                        <router-link to="/" class="footer-menu__link">About us</router-link>
                        <router-link to="/" class="footer-menu__link">Vacancies</router-link>
                        <router-link to="/" class="footer-menu__link">Contact us</router-link>
                        <router-link to="/" class="footer-menu__link">Privacy</router-link>
                        <router-link to="/" class="footer-menu__link">Returns policy</router-link>
                    </div>
                </div>
                <div class="footer-subscribe">
                    <span class="footer-subscribe__title">Join our mailing list</span>
                    <SubscribeForm colorButton="white" bgInput="rgba(255, 255, 255, 0.15)" colorText="#fff" />
                </div>
            </div>
            <div class="footer-bottom">
                <span class="footer-bottom__copyright">
                    Copyright 2022 Avion LTD
                </span>
                <div class="footer-bottom-socials">
                    <a href="#" class="footer-bottom-socials__link">
                        <img src="/svg/Logo--linkedin.svg" alt="linkedin">
                    </a>
                    <a href="#" class="footer-bottom-socials__link">
                        <img src="/svg/Logo--facebook.svg" alt="facebook">
                    </a>
                    <a href="#" class="footer-bottom-socials__link">
                        <img src="/svg/Logo--instagram.svg" alt="instagram">
                    </a>
                    <a href="#" class="footer-bottom-socials__link">
                        <img src="/svg/Logo--skype.svg" alt="skype">
                    </a>
                    <a href="#" class="footer-bottom-socials__link">
                        <img src="/svg/Logo--twitter.svg" alt="twitter">
                    </a>
                    <a href="#" class="footer-bottom-socials__link">
                        <img src="/svg/Logo--pinterest.svg" alt="pinterest">
                    </a>
                </div>
            </div>

        </div>
    </footer>
</template>

<script setup>
import SubscribeForm from '@/components/SubscribeForm.vue'
</script>

<style lang="scss" scoped>
.footer {
    background: var(--dark-primary);
    color: #fff;

    &-content {
        padding: 58px 82px 25px 82px;

        @media screen and (max-width: 1024px) {
            padding: 58px 30px 82px 30px;
        }

        @media screen and (max-width: 767px) {
            padding: 40px 30px 20px 30px;
            //margin: 0 -24px;
        }
    }

    &-top {
        display: grid;
        grid-template-columns: 540px 1fr;
        column-gap: 100px;
        border-bottom: 1px solid var(--primary);
        padding-bottom: 48px;

        @media screen and (max-width: 1150px) {
            column-gap: 10px;
            grid-template-columns: 450px 1fr;
        }

        @media screen and (max-width: 1024px) {
            grid-template-columns: repeat(2, 1fr);
        }

        @media screen and (max-width: 767px) {
            grid-template-columns: repeat(1, 1fr);
        }
    }

    &-menu {
        display: grid;
        grid-template-columns: repeat(3, 1fr);

        @media screen and (max-width: 1024px) {
            grid-template-columns: repeat(2, 1fr);
        }
        @media screen and (max-width: 767px) {
            gap: 40px 100px;
            margin-bottom: 40px;
        }

        &__title {
            font-family: var(--clash);
            display: block;
            margin-bottom: 12px;
        }

        &__link {
            display: block;
            color: #fff;
            font-size: 14px;
            text-decoration: none;
            margin-bottom: 12px;

            &:last-child {
                margin-bottom: 0;
            }

            &:hover {
                text-decoration: underline;
            }
        }
    }

    &-subscribe {
        &__title {
            font-family: var(--clash);
            display: block;
            margin-bottom: 16px;
        }
    }

    &-bottom {
        padding-top: 22px;
        display: flex;
        justify-content: space-between;

        &__copyright {
            @media screen and (max-width: 767px) {
                margin: auto;
                //margin: 0 -24px;
            }

            font-size: 14px;
        }

        &-socials {
            display: flex;
            align-items: center;

            @media screen and (max-width: 767px) {
                display: none;
                //margin: 0 -24px;
            }

            &__link {
                margin: 0 12px;

                &:hover {
                    opacity: 0.8;
                }
            }
        }
    }
}
</style>