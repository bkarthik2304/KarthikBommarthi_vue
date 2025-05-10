<template>
  <div class="container">
    <div class="card-grid">
      <BrandCard
        v-for="(brand, index) in brands"
        :key="brand.brandName"
        :brand="brand"
        :index="index" 
      />
    </div>
  </div>
</template>

<script>
import BrandCard from './BrandCard.vue'

export default {
  components: { BrandCard },
  data() {
    return {
      brands: []
    }
  },
  async mounted() {
    const res = await fetch('https://apparels-hub.onrender.com/api')
    this.brands = await res.json()
  }
}
</script>

<style scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
}

.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2.5rem;
}
</style>
