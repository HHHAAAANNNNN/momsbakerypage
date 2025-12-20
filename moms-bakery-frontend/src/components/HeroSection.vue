<template>
  <section id="hero" class="hero">
    <!-- Video Background -->
    <video autoplay muted loop playsinline class="hero-video">
      <source src="/src/assets/breads/breadv3.mp4" type="video/mp4">
    </video>
    
    <!-- Overlay untuk meningkatkan keterbacaan teks -->
    <div class="video-overlay"></div>
    
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
</script>

<style scoped>
.hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 8rem 2rem 4rem;
  position: relative;
  overflow: hidden;
  background: #3E2723;
}

/* Video Background */
.hero-video {
  position: absolute;
  top: 50%;
  left: 50%;
  min-width: 100%;
  min-height: 100%;
  width: auto;
  height: auto;
  transform: translate(-50%, -50%);
  object-fit: cover;
  z-index: 0;
}

/* Overlay untuk meningkatkan keterbacaan */
.video-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background: linear-gradient(
    135deg,
    rgba(255, 248, 240, 0.75) 0%,
    rgba(253, 245, 230, 0.7) 40%,
    rgba(250, 233, 208, 0.65) 70%,
    rgba(245, 222, 179, 0.6) 100%
  );
  z-index: 1;
  pointer-events: none;
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
  z-index: 3;
}

@keyframes pulse {
  0%, 100% {
    opacity: 0.6;
  }
  50% {
    opacity: 1;
  }
}

/* Hero content */
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
  text-shadow: 0 2px 6px rgba(62, 39, 35, 0.15);
}

/* SUBHEADING - Solusi Readability tanpa Overlay Baru */
.hero-subheading {
  font-family: 'Quicksand', sans-serif;
  font-size: 24px;
  font-weight: 400;
  color: #5D4037; /* Lebih gelap dari #8D6E63 */
  margin-bottom: 3rem;
  line-height: 1.4;
  max-width: 900px;
  margin-left: auto;
  margin-right: auto;
  
  /* Text shadow ganda untuk kontras maksimal */
  text-shadow: 
    0 2px 4px rgba(62, 39, 35, 0.25),
    0 0 8px rgba(255, 255, 255, 0.15);
  
  /* Soft background hanya untuk teks */
  background: rgba(255, 254, 250, 0.75);
  backdrop-filter: blur(4px);
  -webkit-backdrop-filter: blur(4px);
  
  /* Padding minimal agar tidak terlihat seperti kotak */
  padding: 8px 20px;
  border-radius: 12px;
  
  /* Border halus untuk memisahkan dari background */
  border: 1px solid rgba(212, 163, 115, 0.2);
  
  /* Shadow halus untuk depth */
  box-shadow: 0 2px 10px rgba(62, 39, 35, 0.05);
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
    padding: 6px 16px; /* Padding lebih kecil untuk mobile */
    line-height: 1.5;
    text-shadow: 
      0 2px 4px rgba(62, 39, 35, 0.3),
      0 0 6px rgba(255, 255, 255, 0.2);
  }
  
  .cta-button {
    font-size: 18px;
    padding: 0.875rem 2.5rem;
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
    padding: 5px 12px; /* Padding minimal untuk small screen */
  }
  
  .cta-button {
    font-size: 16px;
    padding: 0.75rem 2rem;
  }
}
</style>