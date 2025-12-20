<template>
  <section id="produk" class="product-section">
    <!-- Bread Section - Kiri Atas -->
    <div class="product-row bread-row">
      <div class="product-slider-container">
        <div class="slider-wrapper">
          <button class="slider-nav prev" @click="slideBread('prev')">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
              <path d="M15 18L9 12L15 6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
          
          <div class="slider-track" ref="breadTrack">
            <div 
              class="product-card" 
              v-for="(product, index) in breadProducts" 
              :key="'bread-' + index"
            >
              <div class="card-image">
                <img :src="product.image" :alt="product.name" />
                <div class="price-tag">{{ product.price }}</div>
              </div>
              <div class="card-content">
                <h4 class="product-name">{{ product.name }}</h4>
                <p class="product-desc">{{ product.desc }}</p>
                <button class="order-btn">Pesan Sekarang!</button>
              </div>
            </div>
          </div>
          
          <button class="slider-nav next" @click="slideBread('next')">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
              <path d="M9 18L15 12L9 6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
        </div>
      </div>
      
      <div class="product-info">
        <h2 class="section-heading">Roti Segar Hari Ini:
        <br/>Roti & Bolu Artisan Tangan dengan Bahan Lokal</h2>
        <p class="section-subheading">
          Dipanggang pagi hari dengan bahan pilihan tanpa pengawet. Tekstur lembut di dalam, renyah di luar — sempurna untuk sarapan keluarga atau acara spesial. Pesan sebelum jam 11 dapat GRATIS ongkir!
        </p>
      </div>
    </div>
    
    <!-- Snack Section - Kanan Bawah -->
    <div class="product-row snack-row">
      <div class="product-info">
        <h2 class="section-heading">Kue Tradisional Nusantara: 
            <br/>Kue Kering & Kripik Renyah dari Resep Turun Temurun</h2>
        <p class="section-subheading">
          Kue khas Indonesia dengan rasa autentik yang dijaga sejak 1998. Kripik singkong pedas, kue nastar premium, dan kastengel keju — cocok untuk oleh-oleh atau teman ngopi. Stok terbatas setiap hari!
        </p>
      </div>
      
      <div class="product-slider-container">
        <div class="slider-wrapper">
          <button class="slider-nav prev" @click="slideSnack('prev')">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
              <path d="M15 18L9 12L15 6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
          
          <div class="slider-track" ref="snackTrack">
            <div 
              class="product-card" 
              v-for="(product, index) in snackProducts" 
              :key="'snack-' + index"
            >
              <div class="card-image">
                <img :src="product.image" :alt="product.name" />
                <div class="price-tag">{{ product.price }}</div>
              </div>
              <div class="card-content">
                <h4 class="product-name">{{ product.name }}</h4>
                <p class="product-desc">{{ product.desc }}</p>
                <button class="order-btn">Pesan Sekarang!</button>
              </div>
            </div>
          </div>
          
          <button class="slider-nav next" @click="slideSnack('next')">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
              <path d="M9 18L15 12L9 6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </button>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

// Import bread images
import bread1 from '@/assets/breads/bread1.jpg'
import bread2 from '@/assets/breads/bread2.jpg'
import bread3 from '@/assets/breads/bread3.jpg'
import bread4 from '@/assets/breads/bread4.jpg'
import bread5 from '@/assets/breads/bread5.jpg'
import bread6 from '@/assets/breads/bread6.jpg'

// Import snack images
import snack1 from '@/assets/snacks/snack1.jpg'
import snack2 from '@/assets/snacks/snack2.jpg'
import snack3 from '@/assets/snacks/snack3.jpg'
import snack4 from '@/assets/snacks/snack4.jpg'
import snack5 from '@/assets/snacks/snack5.jpg'
import snack6 from '@/assets/snacks/snack6.jpg'

const breadTrack = ref(null)
const snackTrack = ref(null)

const breadProducts = ref([
  {
    image: bread1,
    name: 'Brownies Tape Premium',
    desc: 'Perpaduan legit tape dan coklat premium',
    price: 'Rp 45.000'
  },
  {
    image: bread2,
    name: 'Roti Sobek Keju',
    desc: 'Lembut dengan taburan keju melimpah',
    price: 'Rp 35.000'
  },
  {
    image: bread3,
    name: 'Bolu Pandan Spesial',
    desc: 'Aroma pandan asli dengan kelembutan khas',
    price: 'Rp 55.000'
  },
  {
    image: bread4,
    name: 'Croissant Butter',
    desc: 'Renyah berlapis dengan butter premium',
    price: 'Rp 28.000'
  },
  {
    image: bread5,
    name: 'Roti Tawar Gandum',
    desc: 'Sehat dan lezat untuk keluarga',
    price: 'Rp 25.000'
  },
  {
    image: bread6,
    name: 'Danish Pastry Coklat',
    desc: 'Pastry premium dengan filling coklat',
    price: 'Rp 32.000'
  }
])

const snackProducts = ref([
  {
    image: snack1,
    name: 'Kripik Singkong Pedas',
    desc: 'Renyah gurih dengan sensasi pedas',
    price: 'Rp 18.000'
  },
  {
    image: snack2,
    name: 'Kue Nastar Premium',
    desc: 'Lumer di mulut dengan selai nanas asli',
    price: 'Rp 75.000'
  },
  {
    image: snack3,
    name: 'Kastengel Keju',
    desc: 'Gurih renyah dengan keju pilihan',
    price: 'Rp 85.000'
  },
  {
    image: snack4,
    name: 'Putri Salju',
    desc: 'Lembut meleleh dengan gula halus',
    price: 'Rp 70.000'
  },
  {
    image: snack5,
    name: 'Kripik Pisang Coklat',
    desc: 'Pisang renyah berlapis coklat premium',
    price: 'Rp 25.000'
  },
  {
    image: snack6,
    name: 'Lidah Kucing',
    desc: 'Renyah tipis dengan rasa butter',
    price: 'Rp 65.000'
  }
])

const slideBread = (direction) => {
  if (!breadTrack.value) return
  const scrollAmount = 130
  const maxScroll = breadTrack.value.scrollWidth - breadTrack.value.clientWidth
  
  if (direction === 'next') {
    if (breadTrack.value.scrollLeft >= maxScroll - 10) {
      breadTrack.value.scrollTo({ left: 0, behavior: 'smooth' })
    } else {
      breadTrack.value.scrollBy({ left: scrollAmount, behavior: 'smooth' })
    }
  } else {
    if (breadTrack.value.scrollLeft <= 10) {
      breadTrack.value.scrollTo({ left: maxScroll, behavior: 'smooth' })
    } else {
      breadTrack.value.scrollBy({ left: -scrollAmount, behavior: 'smooth' })
    }
  }
}

const slideSnack = (direction) => {
  if (!snackTrack.value) return
  const scrollAmount = 130
  const maxScroll = snackTrack.value.scrollWidth - snackTrack.value.clientWidth
  
  if (direction === 'next') {
    if (snackTrack.value.scrollLeft >= maxScroll - 10) {
      snackTrack.value.scrollTo({ left: 0, behavior: 'smooth' })
    } else {
      snackTrack.value.scrollBy({ left: scrollAmount, behavior: 'smooth' })
    }
  } else {
    if (snackTrack.value.scrollLeft <= 10) {
      snackTrack.value.scrollTo({ left: maxScroll, behavior: 'smooth' })
    } else {
      snackTrack.value.scrollBy({ left: -scrollAmount, behavior: 'smooth' })
    }
  }
}
</script>

<style scoped>
.product-section {
  height: 100vh;
  padding: 2rem 3rem;
  padding-top: 5rem;
  background-color: #FFF8F0;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 0.5rem;
  box-sizing: border-box;
  background-image: url("data:image/svg+xml,%3Csvg width='100' height='100' viewBox='0 0 100 100' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M11 18c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm48 25c3.866 0 7-3.134 7-7s-3.134-7-7-7-7 3.134-7 7 3.134 7 7 7zm-43-7c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm63 31c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM34 90c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zm56-76c1.657 0 3-1.343 3-3s-1.343-3-3-3-3 1.343-3 3 1.343 3 3 3zM12 86c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm28-65c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm23-11c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-6 60c2.21 0 4-1.79 4-4s-1.79-4-4-4-4 1.79-4 4 1.79 4 4 4zm29 22c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zM32 63c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm57-13c2.76 0 5-2.24 5-5s-2.24-5-5-5-5 2.24-5 5 2.24 5 5 5zm-9-21c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM60 91c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM35 41c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2zM12 60c1.105 0 2-.895 2-2s-.895-2-2-2-2 .895-2 2 .895 2 2 2z' fill='%23D4A373' fill-opacity='0.03' fill-rule='evenodd'/%3E%3C/svg%3E");
}

.product-row {
  display: grid;
  grid-template-columns: 2fr 1fr;
  gap: 2rem;
  max-width: 1400px;
  margin: 0 auto;
  align-items: center;
}

.bread-row {
  margin-bottom: 0;
}

.snack-row {
  grid-template-columns: 1fr 2fr;
}

/* Product Info */
.product-info {
  padding: 1.5rem;
}

.section-heading {
  font-family: 'Playfair Display', serif;
  font-size: 28px;
  font-weight: 700;
  color: #3E2723;
  margin-bottom: 2rem;
  line-height: 1.2;
}

.section-subheading {
  font-family: 'Quicksand', sans-serif;
  font-size: 16px;
  font-weight: 400;
  color: #5D4037;
  line-height: 1.6;
}

/* Slider Container */
.product-slider-container {
  position: relative;
  padding: 0.5rem 0;
  width: 100%;
}

.slider-wrapper {
  display: flex;
  align-items: center;
  gap: 0.75rem;
}

.slider-track {
  display: flex;
  gap: 1rem;
  overflow-x: auto;
  scroll-behavior: smooth;
  padding: 0.5rem 0.25rem;
  scrollbar-width: none;
  -ms-overflow-style: none;
  width: calc(240px * 2 + 1.5rem);
  flex: 1;
}

.slider-track::-webkit-scrollbar {
  display: none;
}

/* Navigation Buttons */
.slider-nav {
  flex-shrink: 0;
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: #FFFFFF;
  border: 2px solid #D4A373;
  color: #D4A373;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
  box-shadow: 0 4px 12px rgba(212, 163, 115, 0.2);
}

.slider-nav svg {
  width: 20px;
  height: 20px;
}

.slider-nav:hover {
  background: #D4A373;
  color: #FFFFFF;
  transform: scale(1.1);
}

/* Product Card */
.product-card {
  flex-shrink: 0;
  width: 240px;
  background: #FFFFFF;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 6px 20px rgba(62, 39, 35, 0.1);
  transition: all 0.3s ease;
}

.product-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 12px 30px rgba(62, 39, 35, 0.15);
}

.card-image {
  position: relative;
  width: 100%;
  height: 150px;
  overflow: hidden;
}

.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s ease;
}

.product-card:hover .card-image img {
  transform: scale(1.08);
}

.price-tag {
  position: absolute;
  top: 10px;
  right: 10px;
  background: rgba(212, 163, 115, 0.95);
  color: #FFFFFF;
  font-family: 'Quicksand', sans-serif;
  font-size: 12px;
  font-weight: 700;
  padding: 5px 10px;
  border-radius: 14px;
  backdrop-filter: blur(4px);
}

.card-content {
  padding: 0.875rem;
  display: flex;
  flex-direction: column;
  height: 130px;
}

.product-name {
  font-family: 'Quicksand', sans-serif;
  font-size: 15px;
  font-weight: 700;
  color: #3E2723;
  margin-bottom: 0.25rem;
}

.product-desc {
  font-family: 'Quicksand', sans-serif;
  font-size: 12px;
  font-weight: 400;
  color: #8D6E63;
  margin-bottom: 0.5rem;
  line-height: 1.4;
  flex: 1;
}

.order-btn {
  width: 100%;
  padding: 0.6rem 1rem;
  background: #D4A373;
  color: #FFFFFF;
  font-family: 'Quicksand', sans-serif;
  font-size: 13px;
  font-weight: 600;
  border: none;
  border-radius: 20px;
  margin-top: auto;
  cursor: pointer;
  transition: all 0.3s ease;
}

.order-btn:hover {
  background: #C89563;
  transform: translateY(-2px);
  box-shadow: 0 4px 15px rgba(212, 163, 115, 0.4);
}

/* Responsive */
@media (max-width: 1200px) {
  .product-row {
    grid-template-columns: 1fr;
    gap: 2rem;
  }
  
  .snack-row {
    grid-template-columns: 1fr;
  }
  
  .snack-row .product-info {
    order: -1;
  }
  
  .section-heading {
    font-size: 40px;
  }
  
  .product-slider-container {
    max-width: 100%;
  }
  
  .slider-track {
    max-width: 100%;
  }
}

@media (max-width: 768px) {
  .product-section {
    padding: 4rem 1rem;
  }
  
  .section-heading {
    font-size: 32px;
  }
  
  .section-subheading {
    font-size: 18px;
  }
  
  .product-card {
    width: 250px;
  }
  
  .slider-nav {
    width: 40px;
    height: 40px;
  }
  
  .bread-row {
    margin-bottom: 4rem;
  }
}

@media (max-width: 480px) {
  .section-heading {
    font-size: 28px;
  }
  
  .section-subheading {
    font-size: 16px;
  }
  
  .product-card {
    width: 220px;
  }
  
  .card-image {
    height: 160px;
  }
  
  .product-name {
    font-size: 18px;
  }
  
  .slider-nav {
    display: none;
  }
}
</style>
