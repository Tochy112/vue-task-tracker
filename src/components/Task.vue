<template>
    <div class="task">
        <h3>{{task.text}}</h3>
        <p>{{task.day}}</p>
    </div>
</template>

<script>
    export default {
        name: "Task",

        props: {
            task: Object,
        }
    }
</script>

<style>
    .task{
        background-color: rgb(155, 153, 153, 0.4);
        padding: 10px;
        border-radius: 5px;
        width: 100%;
        height: fit-content;
        margin: 10px 0;
    }
    .task h3{
        margin-bottom: 5px;
    }
</style>