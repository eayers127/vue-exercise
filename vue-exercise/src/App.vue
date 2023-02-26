<script setup>
import ExerciseTable from '@/components/ExerciseTable.vue';
import ExerciseForm from './components/ExerciseForm.vue';
</script>

<template>
  <div id="app">
    <h1>Exercise App</h1>
    <exercise-form @add:exercise="addExercise"/>
    <exercise-table :exercises="exercise"/>
  </div>
</template>

<script>
  export default {
    name: 'app',
    components: {
      ExerciseTable,
      ExerciseForm,
    },
    data() {
      return {
        exercises: [
          {
            id: 1,
            exercise: "",
            muscules: "",
            duration: ""
          }
        ]
      }
    }
  }
</script>

<style scoped>
</style>
