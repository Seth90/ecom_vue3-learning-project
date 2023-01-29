<template>
    <div class="ideas">
        <HeroInformation
            title="It started with a small idea"
            description="A global brand with local beginnings, our story begain in a small studio in South London in early 2014"
            link="#"
            background="var(--dark-primary)"
            colorTitle="#fff"
            colorDescription="#fff"
        />
        <img src="/imgs/room.jpg" alt="room" class="ideas-image">
        
    </div>
</template>

<script setup>
import HeroInformation from '@/Components/HeroInformation.vue'
</script>

<style lang="scss" scoped>
.ideas {
    padding: 0 80px;
    margin-bottom: 60px;
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    grid-column-gap: 16px;

    @media screen and (max-width: 767px) {
        padding: 0px 24px 32px 24px;
        grid-template-columns: repeat(1, 1fr);
        gap: 24px;
    }
    &-image {
        width: 100%;
        height: 100%;
        object-fit: cover;
    }
}
</style>