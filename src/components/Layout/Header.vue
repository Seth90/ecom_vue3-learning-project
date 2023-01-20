<template>
    <header class="header">
        <div class="header-top">
            <div class="header-top-search">
                <img src="/svg/header-search.svg" alt="Search">
            </div>
            <a href="#" class="header-logo">Avion</a>
            <div class="header-top-right">
                <div href="#" class="header-top-right__cart">
                    <a href="">
                        <img src="/svg/header-cart.svg" alt="cart">
                    </a>
                </div>
                <div href="#" class="header-top-righh__user">
                    <a href="">
                        <img src="/svg/header-user.svg" alt="cart">
                    </a>
                </div>
            </div>
        </div>
    </header>
</template>

<style lang="scss" scoped>
.header {
    height: 132px;
    background: white;
    &-top {
        display: flex;
        justify-content: space-between;
        height: 70px;
        align-items: center;
        &-right {
            display: flex;
            align-items: center;
            
            &__cart {
                margin-right: 16px;
            }
        }
    }
    &-logo {
        color: #22202E;
        font-size: 24px;
        text-decoration: none;
        font-family: 'Clash Display', sans-serif;
        &:hover {
            text-decoration: underline;
        }
    }
}
</style>