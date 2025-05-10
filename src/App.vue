<template>
  <div class="app-container">
    <header class="main-header">
      <h1>Apparels Hub</h1>
    </header>
    <BrandList />
  </div>
</template>

<script>
import BrandList from './components/BrandList.vue'

export default {
  components: { BrandList }
}
</script>

<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
}

.app-container {
  background-color: #f0f0f0;
  min-height: 100vh;
}

.main-header {
  background: linear-gradient(to right,rgb(25, 39, 73),rgb(66, 125, 208));
  color: white;
  padding: 1rem;
  text-align: center;
  font-size: 1rem;
  font-weight: bold;
  border-radius: 15px; /* Rounded corners */
}
</style>
