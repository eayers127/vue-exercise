<template>
    <div id="exercise-table">
        <table>
            <thead>
                <tr>
                    <th>Exercise</th>
                    <th>Muscules Worked</th>
                    <th>Duration(minutes)</th>
                </tr>
            </thead>
            <tbody>
                <tr v-for="exercise in exercises" :key="exercise.id">

                    <td>
                        <input type="text" v-model="exercise.description"/>
                    </td>

                    <td>
                        <input type="text" v-model="exercise.muscules"/>
                    </td>

                    <td>
                        <input type="text" v-model="exercise.duration"/>
                    </td>

                    <td>
                        <button>Edit</button>
                        <!-- <button @click = emit('past', exercise), $emit('delete', exercise.id)>Delete</button> -->
                    </td>

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
        },
        data() {
            return {
                editing: null
            }
    },
    methods: {
        handleEdit(id) {
            this.editing = id
        }
    }
}
</script>