<template>
    <div class="page">
        <div class="content">
      <!-- Red button counting by one through 10 and restarting -->
      <CountButton :increment="1" color="red" />
      <!-- blue button - counting by 2 and going up till 10 -->
      <CountButton :increment="2" color="blue" />
        </div>
    </div>
  </template>
    
    <script>
    import CountButton from '~/components/CountButton.vue';
    
    export default {
      components: {
        CountButton,
      },
    };
    </script>
    
<style>
.page {
  background-color: #2c3e50;
  display: flex;
  flex-direction: column;
  min-height: 100vh;
}

.content {
  flex-grow: 1;
  padding: 20px;
  text-align: center;
}

/* Sticky footer styles */
.Footer {
  margin-top: auto;
  background-color: #2c3e50;
  color: #ecf0f1;
  padding: 10px;
  text-align: center;
}
</style>
