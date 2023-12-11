<template>
  <div>
    <input
      type="text"
      placeholder="Search products"
      v-model="search"
      @input="handleSearch"
      class="search-input"
    />
    <div class="productsContainer">
      <div v-for="product in filteredProducts.slice(0, 20)" :key="product.id" class="product">
        <h3>{{ product.title }}</h3>
        <p>Price: ${{ product.price }}</p>
        <img :src="product.image" :alt="product.title" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      search: '',
      products: [],
      filteredProducts: [],
    };
  },
  mounted() {
    this.fetchProducts();
  },
  methods: {
    fetchProducts() {
      fetch('https://fakestoreapi.com/products')
        .then((res) => res.json())
        .then((data) => {
          this.products = data;
          this.filteredProducts = data;
        });
    },
    handleSearch() {
      if (this.search === '') {
        this.filteredProducts = this.products;
      } else {
        this.filteredProducts = this.products.filter((product) =>
          product.title.toLowerCase().includes(this.search.toLowerCase())
        );
      }
    },
  },
};
</script>

<style scoped>
/* Scoped styles for your component */
.search-input {
  width: 100%;
  padding: 10px;
  font-size: 16px;
  border: 2px solid #2c3e50; /* Match the color of your page */
  border-radius: 4px;
  background-color: #ecf0f1; /* Match the background color of your page */
  color: #2c3e50; /* Match the text color of your page */
}
</style>
