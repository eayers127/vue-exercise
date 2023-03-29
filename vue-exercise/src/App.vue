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
    },
    methods:{
      addExercise(exercise) {
        const lastId = this.exercises.length > 0 ? this.exercises[this.exercises.length -1].id: 0
        const id = lastId +1

        const newExercise = {
          id,
          ...exercise
        }

        this.exercises = [...this.exercises, newExercise]
      },

      deleteExercise(id) {
        this.exercises = this.exercises.filter(
          exercise => exercise.id !== id
        )
      },

      editExercise(id, editedExercise) {
        exercises = exercises.map(exercise => {
          exercise.id === id ? editedExercise : exercise
        })
      }
    }
  }
</script>

<style scoped>
</style>
