<template>
  <Nav />
  <Thank />
</template>

<script>
import Nav from './components/Nav.vue'
import Thank from './components/Thank.vue'

export default {
  components: { Nav, Thank },
  name: 'App',
}
</script>

<style scoped>
.app-container {
  background-color: #e0f7fa;
  color: #0277bd;
  text-align: center;
  padding: 50px;
  font-family: 'Comic Sans MS', cursive, sans-serif;
  height: 100vh;
}

.title {
  font-size: 3em;
  margin-bottom: 20px;
}

.description {
  font-size: 1.5em;
}
</style>
