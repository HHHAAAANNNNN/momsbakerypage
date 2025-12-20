<script setup>
import GooeyNav from './components/GooeyNav.vue'
import HeroSection from './components/HeroSection.vue'
import ProductSection from './components/ProductSection.vue'
</script>

<template>
  <div class="app">
    <GooeyNav />
    <HeroSection />
    <ProductSection />
  </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  margin: 0;
  padding: 0;
  background: #FFF8F0;
}

#app {
  width: 100%;
  min-height: 100vh;
  background: #FFF8F0;
}

.app {
  width: 100%;
  min-height: 100vh;
  background: #FFF8F0;
}
</style>
