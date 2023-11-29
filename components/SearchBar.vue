<template>
  <div>
    <input
      type="text"
      placeholder="Search products"
      v-model="search"
      @input="handleSearch"
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

<style>
  /* should i put it here? */
  /* .productsContainer {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    max-width: 1200px;
    margin: 0 auto;
  }

  .product {
    width: 200px; 
    border: 2px solid darkgray;
    margin: 10px;
    padding: 8px;
    text-align: center;
    border-radius: 8px;
    overflow: hidden;
  }

  .product img {
    max-width: 100%;
    max-height: 100%;
    object-fit: contain;
    border-radius: 6px;
  } */
</style>
