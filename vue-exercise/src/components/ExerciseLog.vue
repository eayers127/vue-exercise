<template>
    <div>
        <table>
            <thead>
                <tr>
                    <th>Exercise Title</th>
                    <th>Muscle Groups</th>
                    <th>Exercise Duration</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="exercise in exerciseLog" :key="exercise.id">
                    <td>{{ exercise.description }}</td>
                    <td>{{ exercise.muscules }}</td>
                    <td>{{ exercise.duration }}</td>
                </tr>
            </tbody>
        </table>
    </div>
</template>

<script>
    export default {
        name: 'exercise-log',
        props: {
            pastExercises: Array,
        },
        methods: {

        }
    }
</script>