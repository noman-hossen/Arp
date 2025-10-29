<template>
  <nav class="cute-nav">
    <h1 class="nav-title">🌸 Arpi x Hers 👀</h1>
  </nav>
</template>

<script>
export default {
  name: 'CuteNav',
}
</script>

<style scoped>
.cute-nav {
  background: linear-gradient(90deg, #ffc0cb 0%, #a2d2ff 100%);

  padding: 15px 20px;

  box-shadow: 0 4px 10px rgba(255, 105, 180, 0.4);

  display: flex;
  align-items: center;
  justify-content: center;
}

.nav-title {
  font-family: 'Comic Sans MS', cursive, sans-serif;

  color: #8a2be2;

  font-size: 1.8rem;
  margin: 0;

  text-shadow:
    1px 1px 0 #fff,
    2px 2px 0 #ffedf9;

  animation: floatTitle 3s ease-in-out infinite alternate;
}

@keyframes floatTitle {
  from {
    transform: translateY(0px);
  }
  to {
    transform: translateY(-3px);
  }
}
</style>
