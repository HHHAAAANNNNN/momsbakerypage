<template>
  <nav class="gooey-nav">
    <div class="nav-container">
      <div class="logo">Logo</div>
      <div class="nav-center">
        <a href="#produk" class="nav-item">Produk</a>
        <a href="#testimoni" class="nav-item">Testimoni</a>
        <a href="#lokasi" class="nav-item">Lokasi</a>
      </div>
      <button class="burger-menu" @click="handleBurgerClick">
        <span></span>
        <span></span>
        <span></span>
      </button>
    </div>
    <svg style="position: absolute; width: 0; height: 0;">
      <defs>
        <filter id="gooey">
          <feGaussianBlur in="SourceGraphic" stdDeviation="10" result="blur" />
          <feColorMatrix
            in="blur"
            mode="matrix"
            values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 20 -10"
            result="gooey"
          />
          <feComposite in="SourceGraphic" in2="gooey" operator="atop" />
        </filter>
      </defs>
    </svg>
  </nav>
</template>

<script setup>
const handleBurgerClick = () => {
  // Untuk sekarang tidak melakukan apa-apa
};
</script>

<style scoped>
.gooey-nav {
  position: fixed;
  top: 0;
  left: 50%;
  transform: translateX(-50%);
  z-index: 1000;
  padding: 1.5rem 2rem;
  background: rgba(255, 255, 255, 0.95);
  backdrop-filter: blur(10px);
  filter: url('#gooey');
  border-radius: 50px;
  margin-top: 1rem;
}

.nav-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 3rem;
}

.logo {
  font-family: 'Playfair Display', serif;
  font-size: 1.5rem;
  font-weight: 700;
  color: #3E2723;
  flex-shrink: 0;
}

.nav-center {
  display: flex;
  align-items: center;
  gap: 2rem;
  flex: 1;
  justify-content: center;
}

.burger-menu {
  display: flex;
  flex-direction: column;
  gap: 5px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0.5rem;
  flex-shrink: 0;
}

.nav-item {
  font-family: 'Quicksand', sans-serif;
  font-size: 1.125rem;
  font-weight: 600;
  color: #3E2723;
  text-decoration: none;
  padding: 0.75rem 1.5rem;
  border-radius: 25px;
  transition: all 0.3s ease;
  position: relative;
  white-space: nowrap;
  z-index: 1;
}

.nav-item::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: #D4A373;
  border-radius: 25px;
  transform: scale(0);
  transition: transform 0.3s ease;
  z-index: -1;
}

.nav-item:hover::before {
  transform: scale(1);
}

.nav-item:hover {
  color: #FFFFFF;
  font-weight: 600;
}

.burger-menu {
  display: flex;
  flex-direction: column;
  gap: 5px;
  background: transparent;
  border: none;
  cursor: pointer;
  padding: 0.5rem;
}

.burger-menu span {
  width: 25px;
  height: 3px;
  background: #3E2723;
  border-radius: 3px;
  transition: all 0.3s ease;
}

.burger-menu:hover span {
  background: #D4A373;
}

@media (max-width: 768px) {
  .nav-container {
    gap: 2rem;
  }

  .nav-center {
    gap: 1rem;
  }
  
  .nav-item {
    font-size: 0.9rem;
    padding: 0.4rem 0.8rem;
  }
}
</style>
