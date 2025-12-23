<template>
  <section id="lokasi" class="lokasi-section">
    <div class="lokasi-container">
      <h2 class="section-heading">Kunjungi Toko Kami</h2>
      
      <!-- Store Info -->
      <div class="store-info">
        <div class="info-item">
          <div class="info-icon">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
              <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
              <circle cx="12" cy="10" r="3" stroke="currentColor" stroke-width="2"/>
            </svg>
          </div>
          <div class="info-text">
            <h4>Alamat</h4>
            <p>Bolu Boling, Probolinggo, Jawa Timur</p>
          </div>
        </div>
        
        <div class="info-item">
          <div class="info-icon">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
              <circle cx="12" cy="12" r="10" stroke="currentColor" stroke-width="2"/>
              <polyline points="12,6 12,12 16,14" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
          <div class="info-text">
            <h4>Jam Operasional</h4>
            <p>Senin - Sabtu: 07:00 - 21:00</p>
            <p>Minggu: 08:00 - 20:00</p>
          </div>
        </div>
        
        <div class="info-item">
          <div class="info-icon">
            <svg width="24" height="24" viewBox="0 0 24 24" fill="none">
              <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </svg>
          </div>
          <div class="info-text">
            <h4>Kontak</h4>
            <p>+62 812-3456-7890</p>
          </div>
        </div>
      </div>

      <div class="lokasi-content">
        <!-- Map Section -->
        <div class="map-container">
          <div class="map-wrapper">
            <iframe 
              src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3953.282478766659!2d113.19112267490705!3d-7.759836992259233!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2dd7ad471c4f5bc3%3A0xa945ccb9f6d7f74b!2sBolu%20Boling!5e0!3m2!1sen!2sid!4v1766475570240!5m2!1sen!2sid"
              width="100%" 
              height="100%" 
              style="border:0;" 
              allowfullscreen="" 
              loading="lazy" 
              referrerpolicy="no-referrer-when-downgrade"
              class="map-iframe"
            ></iframe>
          </div>
        </div>
        
        <!-- Gallery Section -->
        <div class="gallery-container">
          <div class="gallery-main">
            <img :src="currentImage" alt="Tampilan Toko Mom's Bakery" class="main-image" />
          </div>
          <div class="gallery-thumbnails">
            <div 
              v-for="(image, index) in galleryImages" 
              :key="index"
              class="thumbnail"
              :class="{ active: currentImageIndex === index }"
              @click="setCurrentImage(index)"
            >
              <img :src="image" :alt="'Toko ' + (index + 1)" />
            </div>
          </div>
        </div>
      </div>
      
      <!-- CTA Button -->
      <a 
        href="https://maps.app.goo.gl/mWia1JGC2vmfsaA68" 
        target="_blank" 
        rel="noopener noreferrer"
        class="cta-button"
      >
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none">
          <path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
          <circle cx="12" cy="10" r="3" stroke="currentColor" stroke-width="2"/>
        </svg>
        <span>Buka di Google Maps</span>
      </a>
    </div>
  </section>
</template>

<script setup>
import { ref, computed } from 'vue'

// Import outside images
import outside1 from '@/assets/outsides/outside1.png'
import outside2 from '@/assets/outsides/outside2.png'
import outside3 from '@/assets/outsides/outside3.png'

const galleryImages = ref([outside1, outside2, outside3])
const currentImageIndex = ref(0)

const currentImage = computed(() => galleryImages.value[currentImageIndex.value])

const setCurrentImage = (index) => {
  currentImageIndex.value = index
}
</script>

<style scoped>
.lokasi-section {
  height: 100vh;
  padding: 5rem 3rem 1.5rem 3rem;
  background: linear-gradient(180deg, #F5EDE4 0%, #FFF8F0 100%);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  box-sizing: border-box;
  overflow: hidden;
}

.lokasi-container {
  max-width: 1400px;
  width: 100%;
  text-align: center;
}

.section-heading {
  font-family: 'Playfair Display', serif;
  font-size: 32px;
  font-weight: 700;
  color: #3E2723;
  margin-bottom: 0.3rem;
  line-height: 1.2;
}

.section-subheading {
  font-family: 'Quicksand', sans-serif;
  font-size: 18px;
  font-weight: 400;
  color: #5D4037;
  margin-bottom: 3rem;
  max-width: 800px;
  margin-left: auto;
  margin-right: auto;
  line-height: 1.6;
}

/* Content Layout */
.lokasi-content {
  display: flex;
  gap: 1rem;
  margin-bottom: 1rem;
  align-items: stretch;
}

/* Map Container */
.map-container {
  flex: 1;
  background: #FFFFFF;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 8px 30px rgba(62, 39, 35, 0.1);
  border: 1px solid rgba(212, 163, 115, 0.1);
}

.map-wrapper {
  width: 100%;
  height: 100%;
  position: relative;
}

.map-iframe {
  border-radius: 16px;
}

/* Gallery Container */
.gallery-container {
  flex: 1;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}

.gallery-main {
  flex: 1;
  background: #FFFFFF;
  border-radius: 16px;
  overflow: hidden;
  box-shadow: 0 8px 30px rgba(62, 39, 35, 0.1);
  border: 1px solid rgba(212, 163, 115, 0.1);
  height: 230px;
}

.main-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  transition: transform 0.4s ease;
}

.gallery-main:hover .main-image {
  transform: scale(1.02);
}

.gallery-thumbnails {
  display: flex;
  gap: 0.5rem;
}

.thumbnail {
  flex: 1;
  height: 42px;
  border-radius: 8px;
  overflow: hidden;
  cursor: pointer;
  border: 2px solid transparent;
  transition: all 0.3s ease;
  box-shadow: 0 4px 15px rgba(62, 39, 35, 0.1);
}

.thumbnail:hover {
  transform: translateY(-3px);
  box-shadow: 0 6px 20px rgba(62, 39, 35, 0.15);
}

.thumbnail.active {
  border-color: #D4A373;
}

.thumbnail img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

/* Store Info */
.store-info {
  display: flex;
  justify-content: center;
  gap: 2rem;
  margin-top: 0.75rem;
  margin-bottom: 1rem;
  flex-wrap: wrap;
}

.info-item {
  display: flex;
  align-items: flex-start;
  gap: 1rem;
  text-align: left;
}

.info-icon {
  width: 40px;
  height: 40px;
  background: linear-gradient(135deg, #D4A373 0%, #C89563 100%);
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #FFFFFF;
  flex-shrink: 0;
}

.info-text h4 {
  font-family: 'Quicksand', sans-serif;
  font-size: 14px;
  font-weight: 700;
  color: #3E2723;
  margin-bottom: 0.15rem;
}

.info-text p {
  font-family: 'Quicksand', sans-serif;
  font-size: 13px;
  font-weight: 400;
  color: #5D4037;
  line-height: 1.4;
}

/* CTA Button */
.cta-button {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  font-family: 'Quicksand', sans-serif;
  font-size: 16px;
  font-weight: 700;
  color: #FFFFFF;
  background: linear-gradient(135deg, #D4A373 0%, #C89563 100%);
  border: none;
  padding: 0.75rem 2rem;
  border-radius: 50px;
  cursor: pointer;
  transition: all 0.3s ease;
  box-shadow: 0 6px 20px rgba(212, 163, 115, 0.35);
  text-decoration: none;
}

.cta-button:hover {
  transform: translateY(-3px);
  box-shadow: 0 10px 30px rgba(212, 163, 115, 0.45);
  background: linear-gradient(135deg, #C89563 0%, #B8854F 100%);
}

.cta-button:active {
  transform: translateY(0);
}

/* Responsive */
@media (max-width: 1024px) {
  .lokasi-content {
    grid-template-columns: 1fr;
  }
  
  .map-wrapper {
    height: 350px;
  }
  
  .gallery-main {
    height: 280px;
  }
  
  .store-info {
    gap: 2rem;
  }
}

@media (max-width: 768px) {
  .lokasi-section {
    padding: 3rem 1.5rem;
  }
  
  .section-heading {
    font-size: 32px;
  }
  
  .section-subheading {
    font-size: 16px;
  }
  
  .map-wrapper {
    height: 300px;
  }
  
  .gallery-main {
    height: 250px;
  }
  
  .thumbnail {
    height: 60px;
  }
  
  .store-info {
    flex-direction: column;
    align-items: center;
    gap: 1.5rem;
  }
  
  .info-item {
    width: 100%;
    max-width: 300px;
  }
  
  .cta-button {
    font-size: 16px;
    padding: 0.875rem 2rem;
  }
}

@media (max-width: 480px) {
  .section-heading {
    font-size: 28px;
  }
  
  .map-wrapper {
    height: 250px;
  }
  
  .gallery-main {
    height: 200px;
  }
  
  .thumbnail {
    height: 50px;
  }
  
  .info-icon {
    width: 40px;
    height: 40px;
  }
}
</style>
