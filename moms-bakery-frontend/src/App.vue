<script setup>
import GooeyNav from './components/GooeyNav.vue'
import HeroSection from './components/HeroSection.vue'
import ProductSection from './components/ProductSection.vue'
import TestimoniSection from './components/TestimoniSection.vue'
import LokasiSection from './components/LokasiSection.vue'
import FooterSection from './components/FooterSection.vue'
</script>

<template>
  <div class="app">
    <GooeyNav />
    <HeroSection />
    <ProductSection />
    <TestimoniSection />
    <LokasiSection />
    <FooterSection />
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
