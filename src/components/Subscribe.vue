<template>
    <div class="subscribe">
        <div class="subscribe-content">
            <h3 class="subscribe-title">Join the club and get the benefits</h3>
            <span class="subscribe-description">Sign up for our newsletter and receive exclusive offers on new ranges,
                sales, pop up stores and more</span>

            <div class="subscribe-checks">
                <div class="subscribe-check">
                    <img src="/svg/Checkmark--filled.svg" alt="check" class="subscribe-check__icon" />
                    <span class="subscribe-check__name">Exclusive offers</span>
                </div>
                <div class="subscribe-check">
                    <img src="/svg/Checkmark--filled.svg" alt="check" class="subscribe-check__icon" />
                    <span class="subscribe-check__name">Free events</span>
                </div>
                <div class="subscribe-check">
                    <img src="/svg/Checkmark--filled.svg" alt="check" class="subscribe-check__icon" />
                    <span class="subscribe-check__name">Large discounts</span>
                </div>
            </div>
            <SubscribeForm />
        </div>

    </div>
</template>

<script setup>
import SubscribeForm from '@/components/SubscribeForm.vue'
</script>

<style lang="scss" scoped>
.subscribe {
    background: url('@/../public/imgs/subscribe.jpg');
    background-size: cover;
    padding: 97px 0 86px 0;

    @media screen and (max-width: 767px) {
        padding: 24px;
        background-image: url('@/../public/imgs/subscribe_mobile.jpg');
        //margin: 0 -24px;
    }
    // @media screen and (max-width: 390px) {
    //     background: url('imgs/subscribe_mobile.jpg');
    // }

    &-content {
        max-width: 500px;
        margin: auto;
        text-align: center;
        color: #fff;

        @media screen and (max-width: 767px) {
            text-align: left;
        }
    }

    &-title {
        display: block;
        margin: 0 0 12px 0;
        font-size: 32px;
        //font-weight: 300;
        font-family: var(--clash);

        @media screen and (max-width: 767px) {
            font-size: 24px;
        }
    }

    &-description {
        display: block;
        font-size: 18px;
        line-height: 1.5;
        margin-bottom: 30px;
        @media screen and (max-width: 767px) {
            font-size: 14px;
        }
    }

    &-checks {
        display: flex;
        justify-content: center;
        margin-bottom: 40px;

        @media screen and (max-width: 767px) {
            flex-direction: column;
            justify-content: left;
            gap: 8px;
        }
    }

    &-check {
        display: flex;
        align-items: center;

        &:nth-child(2) {
            margin: 0 36px;

            @media screen and (max-width: 767px) {
                margin: 0;
            }
        }

        &__icon {
            margin-right: 9px;
        }
    }
}
</style>