<template>
    <div @dblclick="$emit('toggle_task', task.id)" :class="[task.reminder ? 'reminder' : '', 'task']">
        <h3>
            {{task.text}}
            <p @click="$emit('delete_task', task.id)">X</p>
        </h3>
        <p>{{task.day}}</p>
    </div>
</template>

<script>
    export default {
        name: "Task",

        props: {
            task: Object,
        },
    }
</script>

<style scoped>
    .task{
        background-color: rgb(155, 153, 153, 0.4);
        padding: 10px;
        border-radius: 5px;
        width: 100%;
        height: fit-content;
        margin: 10px 0;
        cursor: pointer;
    }
    .task h3{
        margin-bottom: 5px;
        display: flex;
        justify-content: space-between;
    }
    .task h3 p{
        color: red;
        font-weight: bold;
    }
    .task.reminder{
        border-left: 5px solid green;
    }
</style>