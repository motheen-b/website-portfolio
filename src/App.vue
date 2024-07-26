<template>
  <div>
    <div class="app-container">
      <Header />
      <Hero />
      <InfoBar />
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Hero from './components/Hero.vue'
import InfoBar from './components/InfoBar.vue'

export default {
  components: {
    Header,
    Hero,
    InfoBar
  }
}
</script>

<style>
  .app-container {
    margin: 0 auto;
    width: 1440px;
    /* border: 2px solid black; */
  }
</style>