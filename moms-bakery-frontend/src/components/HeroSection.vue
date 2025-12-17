<template>
  <section class="hero">
    <!-- Particle System - Baru dan Dramatis -->
    <div class="particle-container">
      <div 
        v-for="(particle, i) in particles" 
        :key="i" 
        class="particle"
        :style="{
          left: particle.left,
          top: particle.top,
          width: particle.size,
          height: particle.size,
          animationDuration: particle.duration,
          animationDelay: particle.delay,
          backgroundColor: particle.color
        }"
      ></div>
    </div>
    
    <div class="hero-content">
      <h1 class="hero-heading">
        Aroma Wangi Brownies Tape Menggoda Tetangga Sebelah!
      </h1>
      <p class="hero-subheading">
        Bolu lembut dengan tekstur sempurna, brownies legit berpadu khas tape, dan kripik renyah gurih — semua dibuat dari resep turun temurun yang telah dinikmati 3 generasi keluarga Indonesia
      </p>
      <button class="cta-button">
        <span class="button-text">Lihat Daftar Produk</span>
      </button>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const particles = ref([])

onMounted(() => {
  // Generate 15 partikel dengan posisi acak
  for (let i = 0; i < 15; i++) {
    particles.value.push({
      left: `${Math.random() * 100}%`,
      top: `${Math.random() * 100}%`,
      size: `${20 + Math.random() * 30}px`,
      duration: `${15 + Math.random() * 20}s`,
      delay: `${Math.random() * 5}s`,
      color: Math.random() > 0.5 ? '#D4A373' : '#F5DEB3' // Alternate colors
    })
  }
})
</script>

<style scoped>
.hero {
  background: linear-gradient(135deg, 
    #FFF8F0 0%, 
    #FDF5E6 40%, 
    #FAE9D0 70%, 
    #F5DEB3 100%
  );
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 8rem 2rem 4rem;
  position: relative;
  overflow: hidden;
}

/* Particle System - Dramatis tapi tetap elegan */
.particle-container {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 1;
}

.particle {
  position: absolute;
  border-radius: 50%;
  filter: blur(15px);
  opacity: 0.4;
  animation: float-particle infinite ease-in-out;
}

@keyframes float-particle {
  0%, 100% {
    transform: translateY(0) translateX(0) scale(1);
  }
  25% {
    transform: translateY(-30px) translateX(20px) scale(1.1);
  }
  50% {
    transform: translateY(-15px) translateX(-10px) scale(0.9);
  }
  75% {
    transform: translateY(15px) translateX(15px) scale(1.05);
  }
}

/* Glow yang lebih terlihat */
.hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: radial-gradient(circle at 65% 35%, 
    rgba(212, 163, 115, 0.25) 0%,  /* Lebih terang */
    transparent 60%
  );
  animation: pulse 8s ease-in-out infinite;
  pointer-events: none;
  z-index: 2;
}

@keyframes pulse {
  0%, 100% {
    opacity: 0.6;
  }
  50% {
    opacity: 1;
  }
}

/* Hero content - dengan depth */
.hero-content {
  max-width: 1000px;
  text-align: center;
  position: relative;
  z-index: 10;
}

.hero-heading {
  font-family: 'Playfair Display', serif;
  font-size: 64px;
  font-weight: 700;
  color: #3E2723;
  margin-bottom: 2rem;
  line-height: 1.2;
}

.hero-subheading {
  font-family: 'Quicksand', sans-serif;
  font-size: 24px;
  font-weight: 400;
  color: #8D6E63;
  margin-bottom: 3rem;
  line-height: 1.4;
  max-width: 900px;
  margin-left: auto;
  margin-right: auto;
}

/* CTA Button - lebih dramatis */
.cta-button {
  font-family: 'Quicksand', sans-serif;
  font-size: 24px;
  font-weight: 700;
  color: #3E2723;
  background: #D4A373;
  border: none;
  padding: 1rem 3rem;
  border-radius: 50px;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(212, 163, 115, 0.3);
  position: relative;
  overflow: hidden;
}

.cta-button::before {
  content: '';
  position: absolute;
  top: -50%;
  left: -50%;
  width: 200%;
  height: 200%;
  background: radial-gradient(circle, rgba(255,255,255,0.3) 0%, transparent 70%);
  transform: rotate(30deg);
  transition: transform 0.6s;
  z-index: 0;
}

.cta-button:hover::before {
  transform: rotate(30deg) translate(30%, 30%);
}

.cta-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(212, 163, 115, 0.4);
  background: #C89563;
}

.button-text {
  position: relative;
  z-index: 1;
}

.cta-button:active {
  transform: translateY(0);
}

@media (max-width: 1024px) {
  .hero-heading {
    font-size: 48px;
  }
  
  .hero-subheading {
    font-size: 20px;
  }
  
  .cta-button {
    font-size: 20px;
  }
}

@media (max-width: 768px) {
  .hero {
    padding: 6rem 1.5rem 3rem;
  }
  
  .hero-heading {
    font-size: 36px;
  }
  
  .hero-subheading {
    font-size: 18px;
  }
  
  .cta-button {
    font-size: 18px;
    padding: 0.875rem 2.5rem;
  }
  
  .particle {
    opacity: 0.25; /* Lebih transparan di mobile */
    filter: blur(10px);
  }
  
  .hero::before {
    opacity: 0.7; /* Kurangi glow di mobile */
  }
}

@media (max-width: 480px) {
  .hero-heading {
    font-size: 28px;
  }
  
  .hero-subheading {
    font-size: 16px;
  }
  
  .cta-button {
    font-size: 16px;
    padding: 0.75rem 2rem;
  }
}
</style>