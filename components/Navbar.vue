<template>
    <nav>
      <div class="container">
        <div class="logo">
          <nuxt-link to="/">Home</nuxt-link>
        </div>
        <ul>
          <li><a href="https://github.com/BriMarie933/nuxt331" target="_blank" rel="noopener noreferrer">GitHub repository</a></li>
          <li><nuxt-link to="/count_page">Count Page</nuxt-link></li>
        </ul>
      </div>
    </nav>
  </template>
  
  <style scoped>
  nav {
    background-color: #2c3e50;
    border-bottom: 2px solid #3498db;
    padding: 1rem 0;
  }
  
  .container {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .logo {
    font-size: 1.5rem;
    color: #ecf0f1;
  }
  
  ul {
    list-style: none;
    margin: 0;
    padding: 0;
    display: flex;
  }
  
  li {
    margin-left: 1.5rem;
    margin-right: .5rem;
  }
  
  nuxt-link {
    text-decoration: none;
    color: #ecf0f1;
    font-weight: bold;
    transition: color 0.3s ease;
  }
  
  nuxt-link:hover {
    color: #3498db;
  }
    /* Use ::v-deep to override global styles for links */
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

  