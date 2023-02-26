<template>
    <div id = "exercise-form">
        <form @submit.prevent="handleSubmit">
            <label>Workout Description:</label>
            <input v-model="exercise.description" type="text">
            <label>What muscules did you focus on:</label>
            <input v-model="exercise.muscules" type="text">
            <label>How long was the workout:</label>
            <input v-model="exercise.duration" type="text">
            <button>Log workout</button>
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
                this.$emit('add:exercise', this.exercise)
            }
        }
    }
</script>