<template>
    <div class="app-container">
        <div class="app-content">
            <Header />
            <Hero />
        </div>
    </div>
</template>

<script>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'

export default {
    components: {
        Header,
        Hero
    }
}
</script>

<style>
    .app-container {
        display: flex;
        justify-content: center;
    }
    .app-content {
        min-width: 320px;
        max-width: 1440px;
        width: 100%;
    }
</style>