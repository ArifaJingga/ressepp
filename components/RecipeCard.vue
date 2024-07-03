<template>
    <div class="recipe-card">
      <h3>{{ recipe.title }}</h3>
      <p>{{ recipe.description }}</p>
    </div>
  </template>
  
  <script>
  export default {
    props: ['recipe']
  }
  </script>
  
  <style scoped>
  .recipe-card {
    border: 1px solid #ccc;
    padding: 10px;
    margin: 10px;
  }
  </style>
  