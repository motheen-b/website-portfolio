<template>
    <div class="app-container">
        <div class="app-content">
            <Header />
            <Hero />
            <AboutMe />
        </div>
    </div>
</template>

<script>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import AboutMe from './components/AboutMe.vue';

export default {
    components: {
        Header,
        Hero,
        AboutMe
    }
}
</script>

<style>
    .app-container {
        display: flex;
        height: 2500px;
        justify-content: center;
        background-color: #f3894b;
    }
    .app-content {
        min-width: 320px;
        max-width: 1440px;
        width: 100%;
    }
</style>