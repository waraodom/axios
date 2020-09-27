<template>
<div id="app">
    <iTune />
</div>
</template>

<script>
import iTune from './components/iTune.vue'
export default {
    name: 'App',
    components: {
        iTune

    }
}
</script>

<style>
#app {
    font-family: 'Athiti', sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}

body {
    background-image: url('https://encrypted-tbn0.gstatic.com/images?q=tbn%3AANd9GcTb_wD_RYFxFilMa1Uj3fPGT1q9W8wgTZrr7w&usqp=CAU');
    background-attachment: fixed;
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
}
</style>
