<template>
  <div>
    <!-- Red button counting by one through 10 and restarting -->
    <CountButton :increment="1" color="red" />
    <!-- blue button - counting by 2 and going up till 10 -->
    <CountButton :increment="2" color="blue" />
    <GitHubLink />
    <SearchBar />
  </div>
</template>
  
  <script>
  import CountButton from '~/components/CountButton.vue';
  import GitHubLink from '~/components/GitHubLink.vue';
  import SearchBar from '~/components/SearchBar.vue';
//  import GitHubLink from '~/components/GitHubLink.vue';
  
  export default {
    components: {
      CountButton,
      GitHubLink,
      SearchBar,
    },
  };
  </script>
  
  <style>
  /* FINALLY GOT IT - import the style sheet and make accessible to components */
    @import '../static/styles/styles.module.css';
  </style> 
  