<template>
    <div>
      <input v-model="title" placeholder="Title">
      <textarea v-model="description" placeholder="Description"></textarea>
      <button @click="addRecipe">Add Recipe</button>
    </div>
  </template>
  
  <script>
  import { db } from '~/plugins/firebase'
  
  export default {
    data() {
      return {
        title: '',
        description: ''
      }
    },
    methods: {
      addRecipe() {
        db.collection('recipes').add({
          title: this.title,
          description: this.description
        }).then(() => {
          this.$router.push('/')
        })
      }
    }
  }
  </script>
  