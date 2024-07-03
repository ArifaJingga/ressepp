<template>
    <div>
      <h1>Recipe List</h1>
      <div v-for="recipe in recipes" :key="recipe.id">
        <RecipeCard :recipe="recipe.data()" />
      </div>
    </div>
  </template>
  
  <script>
  import { db } from '~/plugins/firebase'
  import RecipeCard from '~/components/RecipeCard'
  
  export default {
    components: {
      RecipeCard
    },
    data() {
      return {
        recipes: []
      }
    },
    async fetch() {
      const snapshot = await db.collection('recipes').get()
      this.recipes = snapshot.docs
    }
  }
  </script>
  