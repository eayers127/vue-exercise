<template>
    <div id="exercise-table">
        <table>
            <thead>
                <tr>
                    <th>Exercise</th>
                    <th>Muscules Worked</th>
                    <th>Duration</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="exercise in exercises" :key="exercise.id">
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
        name: 'exercise-table',
        props: {
            exercises: Array,
        }
    }
</script>