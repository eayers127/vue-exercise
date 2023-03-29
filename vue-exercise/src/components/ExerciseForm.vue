<template>
    <div id = "exercise-form">
        <form @submit.prevent="handleSubmit">
            <label for="description">Workout Description:</label>
            <input v-model="exercise.description" type="text" id="description">
            <label for="muscles">What muscules did you focus on:</label>
            <input v-model="exercise.muscules" type="text" id="muscles">
            <label for="duration">How long was the workout:</label>
            <input v-model="exercise.duration" type="text" id="duration">

            <button @click="$emit('add', handleSubmit())">Log workout</button>
        </form>
    </div>
</template>

<script>
    export default {
        name: 'exercise-form',
        data() {
            return {
                exercise: {
                    description: '',
                    muscules: '',
                    duration: '',
            },
            }    
        },
        methods: {
            handleSubmit() {
                this.$emit('add', this.exercise)
            }
        }
    }
</script>