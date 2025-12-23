<template>
  <section id="testimoni" class="testimoni-section">
    <div class="testimoni-container">
      <h2 class="section-heading">Apa Kata Mereka yang Sudah Mencoba?</h2>
      <p class="section-subheading">Lebih dari 10.000 pelanggan puas dengan produk kami</p>
      
      <div class="testimoni-slider">
        <button class="slider-nav prev" @click="slideTestimoni('prev')">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
            <path d="M15 18L9 12L15 6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </button>
        
        <div class="slider-track" ref="testimoniTrack">
          <div 
            class="testimoni-card" 
            v-for="(testimoni, index) in testimonials" 
            :key="'testimoni-' + index"
          >
            <div class="card-image">
              <img :src="testimoni.image" :alt="testimoni.name" />
            </div>
            <div class="card-content">
              <h4 class="customer-name">{{ testimoni.name }}</h4>
              <p class="customer-comment">{{ testimoni.comment }}</p>
              <div class="rating-container">
                <div class="stars">
                  <span v-for="star in 5" :key="star" class="star" :class="{ filled: star <= testimoni.rating }">★</span>
                </div>
                <span class="rating-count">({{ testimoni.reviewCount }})</span>
              </div>
            </div>
          </div>
        </div>
        
        <button class="slider-nav next" @click="slideTestimoni('next')">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
            <path d="M9 18L15 12L9 6" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          </svg>
        </button>
      </div>
      
      <p class="bottom-tagline">Jadilah bagian dari keluarga besar Mom's Bakery!</p>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

// Import people images
import woman1 from '@/assets/people/woman1.jpg'
import woman2 from '@/assets/people/woman2.jpg'
import woman3 from '@/assets/people/woman3.jpg'
import woman4 from '@/assets/people/woman4.jpg'
import woman5 from '@/assets/people/woman5.jpg'
import man1 from '@/assets/people/man1.jpg'
import man2 from '@/assets/people/man2.jpg'
import man3 from '@/assets/people/man3.jpg'

const testimoniTrack = ref(null)

const testimonials = ref([
  {
    image: woman1,
    name: 'Siti Rahayu',
    comment: 'Brownies tape-nya juara banget! Anak-anak di rumah langsung habiskan dalam sehari. Pasti repeat order!',
    rating: 5,
    reviewCount: 127
  },
  {
    image: woman2,
    name: 'Dewi Kartika',
    comment: 'Sudah langganan 3 tahun untuk acara arisan. Teman-teman selalu tanya beli dimana. Recommended!',
    rating: 5,
    reviewCount: 156
  },
  {
    image: man2,
    name: 'Ahmad Fauzi',
    comment: 'Roti sobek kejunya lembut banget, kejunya melimpah. Cocok untuk sarapan keluarga setiap hari.',
    rating: 4,
    reviewCount: 73
  },
  {
    image: woman3,
    name: 'Maya Putri',
    comment: 'Kastengel keju-nya renyah dan gurih! Sudah jadi tradisi Lebaran di keluarga kami. Worth it!',
    rating: 5,
    reviewCount: 201
  },
  {
    image: man3,
    name: 'Rizky Pratama',
    comment: 'Kripik singkong pedasnya nagih! Pedesnya pas, renyahnya tahan lama. Favorit buat ngemil.',
    rating: 5,
    reviewCount: 94
  },
  {
    image: woman4,
    name: 'Linda Wijaya',
    comment: 'Bolu pandan spesialnya harum dan lembut. Ibu mertua sampai minta resepnya, haha!',
    rating: 5,
    reviewCount: 118
  },
  {
    image: woman5,
    name: 'Anisa Nurhaliza',
    comment: 'Pelayanannya ramah, pengirimannya cepat. Kue datang masih fresh dan packagingnya rapi!',
    rating: 5,
    reviewCount: 142
  }
])

const slideTestimoni = (direction) => {
  if (!testimoniTrack.value) return
  const scrollAmount = 300
  const maxScroll = testimoniTrack.value.scrollWidth - testimoniTrack.value.clientWidth
  
  if (direction === 'next') {
    if (testimoniTrack.value.scrollLeft >= maxScroll - 10) {
      testimoniTrack.value.scrollTo({ left: 0, behavior: 'smooth' })
    } else {
      testimoniTrack.value.scrollBy({ left: scrollAmount, behavior: 'smooth' })
    }
  } else {
    if (testimoniTrack.value.scrollLeft <= 10) {
      testimoniTrack.value.scrollTo({ left: maxScroll, behavior: 'smooth' })
    } else {
      testimoniTrack.value.scrollBy({ left: -scrollAmount, behavior: 'smooth' })
    }
  }
}
</script>

<style scoped>
.testimoni-section {
  min-height: 100vh;
  padding: 5rem 3rem 3rem 3rem;
  background: linear-gradient(180deg, #FFF8F0 0%, #F5EDE4 100%);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  box-sizing: border-box;
}

.testimoni-container {
  max-width: 1400px;
  width: 100%;
  text-align: center;
  margin-top: 1rem;
}

.section-heading {
  font-family: 'Playfair Display', serif;
  font-size: 42px;
  font-weight: 700;
  color: #3E2723;
  margin-bottom: 1rem;
  line-height: 1.2;
}

.section-subheading {
  font-family: 'Quicksand', sans-serif;
  font-size: 18px;
  font-weight: 400;
  color: #5D4037;
  margin-bottom: 1rem;
}

/* Slider Container */
.testimoni-slider {
  display: flex;
  align-items: center;
  gap: 1.5rem;
  margin-bottom: 3rem;
}

.slider-track {
  display: flex;
  gap: 1.5rem;
  overflow-x: auto;
  scroll-behavior: smooth;
  padding: 1rem 0.5rem;
  scrollbar-width: none;
  -ms-overflow-style: none;
  flex: 1;
}

.slider-track::-webkit-scrollbar {
  display: none;
}

/* Navigation Buttons */
.slider-nav {
  flex-shrink: 0;
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: #FFFFFF;
  border: 2px solid #D4A373;
  color: #D4A373;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(212, 163, 115, 0.25);
}

.slider-nav:hover {
  background: #D4A373;
  color: #FFFFFF;
  transform: scale(1.1);
  box-shadow: 0 6px 20px rgba(212, 163, 115, 0.4);
}

/* Testimoni Card */
.testimoni-card {
  flex-shrink: 0;
  width: 280px;
  background: #FFFFFF;
  border-radius: 20px;
  overflow: hidden;
  box-shadow: 0 8px 30px rgba(62, 39, 35, 0.1);
  transition: all 0.4s ease;
  border: 1px solid rgba(212, 163, 115, 0.1);
}

.testimoni-card:hover {
  transform: translateY(-10px);
  box-shadow: 0 20px 40px rgba(62, 39, 35, 0.15);
}

.card-image {
  width: 100%;
  height: 200px;
  overflow: hidden;
  background: linear-gradient(135deg, #F5EDE4 0%, #E8DDD4 100%);
}

.card-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s ease;
}

.testimoni-card:hover .card-image img {
  transform: scale(1.05);
}

.card-content {
  padding: 1.5rem;
  text-align: left;
}

.customer-name {
  font-family: 'Playfair Display', serif;
  font-size: 18px;
  font-weight: 700;
  color: #3E2723;
  margin-bottom: 0.75rem;
}

.customer-comment {
  font-family: 'Quicksand', sans-serif;
  font-size: 14px;
  font-weight: 400;
  color: #5D4037;
  line-height: 1.6;
  margin-bottom: 1rem;
  min-height: 66px;
}

.rating-container {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.stars {
  display: flex;
  gap: 2px;
}

.star {
  font-size: 16px;
  color: #E0D5C9;
  transition: color 0.3s ease;
}

.star.filled {
  color: #D4A373;
}

.rating-count {
  font-family: 'Quicksand', sans-serif;
  font-size: 13px;
  color: #8D6E63;
}

.bottom-tagline {
  font-family: 'Quicksand', sans-serif;
  font-size: 16px;
  font-weight: 500;
  color: #5D4037;
  font-style: italic;
}

/* Responsive */
@media (max-width: 1200px) {
  .section-heading {
    font-size: 36px;
  }
  
  .testimoni-card {
    width: 260px;
  }
}

@media (max-width: 768px) {
  .testimoni-section {
    padding: 3rem 1.5rem;
  }
  
  .section-heading {
    font-size: 28px;
  }
  
  .section-subheading {
    font-size: 16px;
  }
  
  .testimoni-card {
    width: 240px;
  }
  
  .card-image {
    height: 160px;
  }
  
  .slider-nav {
    width: 40px;
    height: 40px;
  }
}

@media (max-width: 480px) {
  .section-heading {
    font-size: 24px;
  }
  
  .testimoni-card {
    width: 220px;
  }
  
  .slider-nav {
    display: none;
  }
  
  .bottom-tagline {
    font-size: 14px;
  }
}
</style>
