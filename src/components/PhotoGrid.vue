<template>
  <div class="thank-you-container">
    <thank-you-message @scrollToGallery="scrollToGallery" />
    <photo-grid :photos="photos" ref="gallerySection" />
    <floating-hearts :hearts="hearts" />
  </div>
</template>

<script setup>
import { ref } from 'vue'
import ThankYouMessage from './ThankYouMessage.vue'
import PhotoGrid from './PhotoGrid.vue'
import FloatingHearts from './FloatingHearts.vue'
import Letter from './Letter.vue'

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
const photos = [
  'https://source.unsplash.com/random/600x600?friends',
  'https://source.unsplash.com/random/600x600?smile',
  'https://source.unsplash.com/random/600x600?fun',
  'https://source.unsplash.com/random/600x600?travel',
  'https://source.unsplash.com/random/600x600?coffee',
  'https://source.unsplash.com/random/600x600?beach',
  'https://source.unsplash.com/random/600x600?selfie',
  'https://source.unsplash.com/random/600x600?sunset',
]
</script>

<style scoped>
/* 🌸 Layout */
.thank-you-container {
  position: relative;
  overflow-x: hidden;
  background: linear-gradient(135deg, #fff5ff, #ffe6f0);
  font-family: 'Comic Neue', cursive;
}
</style>
