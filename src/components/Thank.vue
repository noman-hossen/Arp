<template>
  <div class="thank-you-container">
    <!-- 🌸 SVG Flower Background Layers -->
    <div class="flower-bg">
      <div class="flower-layer layer1" v-html="flowerSVG"></div>
      <div class="flower-layer layer2" v-html="flowerSVG"></div>
      <div class="flower-layer layer3" v-html="flowerSVG"></div>
    </div>

    <!-- 💖 Foreground Message -->
    <section class="message">
      <h1 class="thank-text">Thank You, Medam! 💕</h1>
      <p class="subtext">I love you so much... 🌷</p>
      <button @click="scrollToGallery" class="btn">Memories 📸</button>
    </section>

    <!-- 💞 Floating Hearts (always visible) -->
    <div class="hearts">
      <div
        v-for="heart in hearts"
        :key="heart.id"
        class="heart"
        :style="{
          left: heart.left + '%',
          animationDelay: heart.delay + 's',
          animationDuration: heart.duration + 's',
        }"
      >
        💖
      </div>
    </div>

    <!-- 🖼️ Memory Photo Grid -->
    <section ref="gallerySection" class="photo-grid-section">
      <h2 class="gallery-title">Our Favorite Memories 🌸</h2>
      <div class="grid">
        <img v-for="(photo, i) in photos" :key="i" :src="photo" alt="memory" />
      </div>
    </section>
  </div>
</template>

<script setup>
import { ref } from 'vue'

/* 🌸 SVG Flower */
const flowerSVG = `
<svg xmlns="http://www.w3.org/2000/svg" width="256" height="256" viewBox="0 0 256 256">
  <g transform="translate(1.4 1.4) scale(2.81 2.81)">
    <path d="M77.265 30.613c-8.193-.58-19.094 3.647-29.002 11.714C61.334 26.591 65.488-.709 44.764.013c-19.108.486-17.755 22.868-2.521 41.743C26.566 28.555-.604 24.317.01 45.004c.389 19.141 22.852 17.869 41.824 2.66C28.272 63.027 24.082 90.364 44.821 89.653c19.156-.477 17.761-22.972 2.427-41.886 15.4 13.526 42.764 17.645 41.993-3.097-.251-9.033-5.386-13.481-12.721-14.046z" fill="#ff3487"/>
    <path d="M57.661 11.951c-6.204 5.384-10.923 16.08-12.225 28.791C43.552 20.372 27.185-1.87 13.042 13.295  -0.125 27.15 16.658 42.02 40.776 44.595 20.357 46.345-1.853 62.56 13.209 76.754c13.81 13.26 28.794-3.523 31.455-27.693 1.273 20.453 17.641 42.746 31.803 27.578 13.208-13.883-3.685-28.803-27.901-31.334C69.538 43.449 91.8 27.012 76.588 12.89c-6.565-6.21-13.341-5.724-18.927-.937z" fill="#ff76ae"/>
    <circle cx="44.936" cy="44.946" r="13.666" fill="#ffdf5a"/>
  </g>
</svg>
`

/* 💞 Floating Hearts */
const hearts = Array.from({ length: 20 }).map((_, i) => ({
  id: i,
  left: Math.random() * 100,
  delay: Math.random() * 2,
  duration: 4 + Math.random() * 3,
}))

/* 📸 Gallery */
const gallerySection = ref(null)
const scrollToGallery = () => {
  gallerySection.value.scrollIntoView({ behavior: 'smooth' })
}

/* Add your real photos here! */
import img1 from '../img/i1.jpg'
import img2 from '../img/i2.jpg'
import img3 from '../img/i3.jpg'
import img4 from '../img/i4.jpg'
import img5 from '../img/i5.jpg'
import img6 from '../img/i6.jpg'
import img7 from '../img/i7.jpg'
import img8 from '../img/i8.jpg'

const photos = [img1, img2, img3, img4, img5, img6, img7, img8]
</script>

<style scoped>
/* 🌸 Layout */
.thank-you-container {
  position: relative;
  overflow-x: hidden;
  background: linear-gradient(135deg, #fff5ff, #ffe6f0);
  font-family: 'Comic Neue', cursive;
}

/* 🌸 Flower Background Layers */
.flower-bg {
  position: fixed;
  inset: 0;
  z-index: 0;
  pointer-events: none;
}
.flower-layer {
  position: absolute;
  width: 120%;
  height: 120%;
  top: -10%;
  left: -10%;
  transform-origin: center;
  opacity: 0.25;
}
.layer1 {
  animation: rotate1 80s linear infinite;
}
.layer2 {
  animation: rotate2 120s linear infinite;
  opacity: 0.35;
  transform: scale(1.2);
}
.layer3 {
  animation: rotate3 180s linear infinite;
  opacity: 0.15;
  transform: scale(1.5);
  filter: blur(2px);
}
@keyframes rotate1 {
  from {
    transform: rotate(0deg) scale(1);
  }
  to {
    transform: rotate(360deg) scale(1.05);
  }
}
@keyframes rotate2 {
  from {
    transform: rotate(0deg) scale(1.2);
  }
  to {
    transform: rotate(-360deg) scale(1.2);
  }
}
@keyframes rotate3 {
  from {
    transform: rotate(0deg) scale(1.5);
  }
  to {
    transform: rotate(720deg) scale(1.5);
  }
}

/* 💕 Hero Section */
.message {
  text-align: center;
  padding: 6rem 1rem 4rem;
  z-index: 2;
  position: relative;
}
.thank-text {
  font-size: 2.5rem;
  color: #ff66b2;
  text-shadow: 2px 2px 8px rgba(255, 105, 180, 0.4);
  animation: bounce 2s infinite ease-in-out;
}
.subtext {
  color: #ff99cc;
  margin-top: 0.5rem;
  font-size: 1.1rem;
}
.btn {
  margin-top: 1.5rem;
  color: white;
  border: none;
  padding: 0.8rem 1.5rem;
  border-radius: 25px;
  cursor: pointer;
  transition: all 0.3s ease;
  font-size: 1rem;
  box-shadow: 0 4px 10px rgba(255, 182, 193, 0.5);
  background-color: #ff66b2;
}
.btn:hover {
  background-color: #ffb6c1;
  transform: scale(1.05);
}

/* 💞 Floating Hearts */
.hearts {
  position: fixed;
  inset: 0;
  pointer-events: none;
  z-index: 1;
}
.heart {
  position: absolute;
  bottom: -30px;
  font-size: 1.8rem;
  animation: floatUp 6s linear infinite;
  opacity: 0.9;
}
@keyframes floatUp {
  0% {
    transform: translateY(0) translateX(0) rotate(0deg) scale(1);
    opacity: 1;
  }
  25% {
    transform: translateY(-25vh) translateX(-10px) rotate(180deg) scale(1.1);
  }
  50% {
    transform: translateY(-50vh) translateX(10px) rotate(360deg) scale(0.95);
  }
  75% {
    transform: translateY(-75vh) translateX(-15px) rotate(540deg) scale(1.1);
  }
  100% {
    transform: translateY(-100vh) translateX(0) rotate(720deg) scale(1);
    opacity: 0;
  }
}

/* 🖼️ Photo Gallery */
.photo-grid-section {
  padding: 3rem 1rem 4rem;
  background: rgba(255, 240, 245, 0.8);
  z-index: 2;
  position: relative;
}
.gallery-title {
  text-align: center;
  font-size: 1.8rem;
  color: #ff66b2;
  margin-bottom: 2rem;
}
.grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr); /* 📱 Mobile first */
  gap: 1rem;
  max-width: 900px;
  margin: 0 auto;
}
.grid img {
  width: 100%;
  height: 160px;
  object-fit: cover;
  border-radius: 15px;
  box-shadow: 0 4px 8px rgba(255, 150, 200, 0.5);
  transition:
    transform 0.4s ease,
    box-shadow 0.4s ease;
}
.grid img:hover {
  transform: scale(1.05);
  box-shadow: 0 6px 12px rgba(255, 100, 180, 0.6);
}

/* 📱 Responsive Breakpoints */
@media (min-width: 600px) {
  .thank-text {
    font-size: 3rem;
  }
  .grid {
    grid-template-columns: repeat(3, 1fr);
  }
}
@media (min-width: 900px) {
  .grid {
    grid-template-columns: repeat(4, 1fr);
  }
}

/* ✨ Little animations */
@keyframes bounce {
  0%,
  100% {
    transform: translateY(0);
  }
  50% {
    transform: translateY(-8px);
  }
}
</style>
