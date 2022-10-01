<template>
    <form @submit="handleSubmit">
        <div>
            <label for="add_task">Task</label>
            <input type="text" v-model="add_task" name="add_task" placeholder="Add Task">
        </div>
        <div>
            <label for="add_time">Day and Time</label>
            <input type="text" v-model="add_time" name="add_time" placeholder="Add Day and Time">
        </div>
        <div id="reminder">
            <label for="reminder">Set Reminder</label>
            <input type="checkbox" v-model="reminder" name="reminder" id="reminder">
        </div>

            <Button text="Save Task"/>    
        </form>
</template>

<script>
    import Button from './Button';

    export default {
        name: "AddTask",
        components: {
            Button,
        },

        data(){
            return {
                "add_task": "",
                "add_time": "",
                "reminder": false
            }
        },

        methods: {
            handleSubmit(e){
                e.preventDefault()

                if(!this.add_task){
                    alert("Please enter a task")
                    return
                }

                const newTask = {
                    id: Math.floor(Math.random()* 100000),
                    text: this.add_task,
                    day: this.add_time,
                    reminder: this.reminder
                }

                this.$emit('add-task', newTask)

                this.add_task = "",
                this.add_time = "",
                this.reminder = ""
            }
        }

    }
</script>

<style scoped>
    form div{
        display: flex;
        flex-direction: column;
    }
    form label{
        margin-top: 10px;
    }
    form input{
        padding: 10px;
        border: 2px solid grey;
        border-radius: 5px;
    }
    form #reminder{
       margin-bottom: 10px;
    }
    form Button{
        width:100%;
        margin-bottom: 10px;
    }
    
</style>