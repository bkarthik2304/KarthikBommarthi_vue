<template>
  <div
    class="card"
    @click="toggleDetails"
    :class="{
      'dark-card': isDark,
      'light-card': !isDark,
    }"
  >
    <div class="card-content">
      <h2 class="brand-title">{{ brand.brandName }}</h2>
      <a
        :href="brand.officialWebsite"
        target="_blank"
        @click.stop
        class="brand-link"
      >
        Visit Website
      </a>

      <div v-if="showDetails" class="brand-details">
        <p><strong>Origin:</strong> {{ brand.originCountry || 'N/A' }}</p>
        <p><strong>Founded:</strong> {{ brand.foundedYear || 'N/A' }}</p>
        <p><strong>Category:</strong> {{ brand.category || 'N/A' }}</p>
        <p><strong>Popular Products:</strong>
          {{ brand.popularProducts ? brand.popularProducts.join(', ') : 'N/A' }}
        </p>
        <p><strong>Price Range:</strong> {{ brand.priceRange || 'N/A' }}</p>
        <p><strong>Availability:</strong>
          {{ brand.globalAvailability ? brand.globalAvailability.join(', ') : 'N/A' }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    brand: Object,
    index: Number,
  },
  data() {
    return {
      showDetails: false,
    };
  },
  methods: {
    toggleDetails() {
      this.showDetails = !this.showDetails;
    },
  },
  computed: {
    isDark() {
      return this.index % 2 === 0;
    },
  },
};
</script>

<style scoped>
.card {
  border-radius: 10px;
  padding: 1.5rem;
  margin: 1rem;
  cursor: pointer;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease;
}

.card:hover {
  transform: scale(1.05);
}

.dark-card {
  background-color: #1f2937;
  color: white;
}

.light-card {
  background-color: white;
  color: black;
  border: 1px solid #ccc;
}

.card-content {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.brand-title {
  font-size: 1.5rem;
  font-weight: bold;
  margin-bottom: 2rem;
}

.brand-link {
  font-size: 1rem;
  text-decoration: underline;
  margin-bottom: 0.5rem;
  color: inherit;
}

.brand-details {
  margin-top: 1rem;
  text-align: left;
  padding-left: 10px;
}

.brand-details p {
  margin: 0.5rem 0;
}

.main-header {
  background: linear-gradient(to right, #111827, #1f2937);
  color: white;
  padding: 2rem;
  text-align: center;
  font-size: 2rem;
  font-weight: bold;
  border-radius: 15px;
}
</style>
