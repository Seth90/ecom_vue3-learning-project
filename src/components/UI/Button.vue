<template>
    <button v-if="type === 'button'" :class="['btn', {
        'btn--dark-primary': color === 'primary',
        'btn--secondary': color === 'secondary',
        'btn--lightGray': color === 'lightgray',
        'btn--white': color === 'white',
        'btn--fullWidth': mobileFullWidth
    }]">
        {{ text }}
    </button>
    <router-link v-else :to="to" :class="['btn', {
        'btn--dark-primary': color === 'primary',
        'btn--secondary': color === 'secondary',
        'btn--lightgray': color === 'lightgray',
        'btn--white': color === 'white',
        'btn--fullWidth': mobileFullWidth
    }]">
        <!-- <slot /> -->
        {{ text }}
    </router-link>
</template>

<script setup>
const props = defineProps({
    background: {
        type: String,
        required: false
    },
    type: {
        type: String,
        default: 'button'
    },
    to: {
        type: String,
        required: false
    },
    color: {
        type: String,
        default: 'primary'
    },
    text: {
        type: String,
        required: true
    },
    mobileFullWidth: {
        type: Boolean,
        default: false
    }
})

</script>

<style lang="scss" scoped>
.btn {
    // background: var(--dark-primary);
    border: none;
    // color: #fff;
    padding: 0 32px;
    display: inline-flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    font-size: 16px;
    height: 56px;
    text-decoration: none;
    white-space: nowrap;
    @media screen and (max-width: 767px){
            padding: 0 15px;
        }
    &:hover {
        text-decoration: underline;
        opacity: 0.8;
    }

    &--dark-primary {
        background: var(--dark-primary);
        color: #fff;
    }

    &--secondary {
        background: rgba(249, 249, 249, 0.15);
        color: #fff;
    }

    &--lightgray {
        background: #F9F9F9;
        color: var(--dark-primary)
    }

    &--white {
        background: #fff;
        color: var(--dark-primary)
    }
    &--fullWidth {
        @media screen and (max-width: 767px){
            width: 100%;
        }
    }

    // color: var(--dark-primary);
    // text-decoration: none;
    // width: 170px;
    // height: 56px;
    // display: flex;
    // align-items: center;
    // justify-content: center;
    // background: rgba(249, 249, 249, 0.15);
    // transition: 0.3s;
    // cursor: pointer;
    // &:hover {
    //     background: rgba(249, 249, 249, 0.30);
    // }

}
</style>