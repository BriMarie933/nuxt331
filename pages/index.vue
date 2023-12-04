<template>
  <div class="home">
    <!-- Red button counting by one through 10 and restarting -->
    <CountButton :increment="1" color="red" />
    <!-- blue button - counting by 2 and going up till 10 -->
    <CountButton :increment="2" color="blue" />
    <GitHubLink />
    <SearchBar />
  </div>
</template>
  
  <script>
  import SearchBar from '~/components/SearchBar.vue';
  
  export default {
    components: {
      SearchBar,
    },
  };
  </script>
  <style scoped>
  .home {
    background-color: #2c3e50; /* Match the background color of the Navbar and Footer */
    color: #ecf0f1; /* Set a text color that contrasts with the background */
    padding: 2rem;
    text-align: center;
    display: flex;
    flex-direction: column;
    min-height: 100vh;
    flex-grow: 1;
    padding: 20px;
    text-align: center;
  }
  
  h1 {
    color: #3498db; /* Set a heading color similar to the Navbar link hover color */
  }  /* Use ::v-deep to override global styles for links */
::v-deep a,
::v-deep nuxt-link {
  color: #3498db; /* Set link color */
  text-decoration: none; /* Remove underline */
}

::v-deep a:hover,
::v-deep nuxt-link:hover {
  color: #2980b9; /* Change link color on hover */
}
  </style>
  <style>
  /* FINALLY GOT IT - import the style sheet and make accessible to components */
    @import '../static/styles/styles.module.css';
  </style> 