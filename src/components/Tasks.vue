<template>

    <div>
        <div :key="task.id" v-for="task in tasks">
            <Task  @toggle_task="$emit('toggle_task', task.id)" @delete_task="$emit('delete_task', task.id)" :task ="task"/>
        </div>
    </div>

</template>

<script>
    import Task from "./Task"

    export default {
        name: "Tasks",

        props: {
            tasks: Array
        },

        components: {
            Task
        },
        emit: [
            "delete_task",
            "toggle_task"
        ],
    }
</script>