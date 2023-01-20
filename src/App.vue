<script setup>
import Header from './components/Layout/Header.vue'
</script>

<template>
  <div class="container">
    <Header/>
  </div>
</template>

<style lang="scss">
@import url('https://fonts.cdnfonts.com/css/satoshi');
@import url('https://fonts.cdnfonts.com/css/clash-display');
* {
    box-sizing: border-box;
}
body {
    font-family: 'Satoshi', sans-serif;
}
.container {
    max-width: 1440px;
    margin: auto;
}
</style>
