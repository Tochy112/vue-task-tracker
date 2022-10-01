<template>
  <div class="container">
      
    <Header @toggle-add-task="toggleAddTask" title="Task Tracker" :showAddTask="showAddTask" /> 

    <div v-show ="showAddTask">
      <AddTask @add-task="addTask" />
    </div> 
    
    <Tasks  @toggle_task="toggleTask" @delete_task="deleteTask" :tasks="tasks"/>

  </div>
</template>

<script>

import Header from './components/Header';
import Tasks from './components/Tasks';
import AddTask from './components/AddTask';

export default {
  name: 'App',

  components: {
    Header,
    Tasks,
    AddTask,
},

  methods: {
    toggleAddTask(){
      this.showAddTask = !this.showAddTask
    },

    addTask(task){
      this.tasks = [...this.tasks, task]
    },

    deleteTask(id){
      confirm("Delete this task?") ?
      this.tasks = this.tasks.filter((task) => task.id !== id)
      : "";
    },

    toggleTask(id){
      this.tasks = this.tasks.map((task) => task.id === id ?
        {...task, reminder: !task.reminder} 
        : task
      )
    }
  },

  data(){
    return{
      tasks: [],
      showAddTask : true
    }
  },

  created(){
    this.tasks = [
      
      // {
      //   id: 1,
      //   text: "Doctors Appointment",
      //   day: "March 1st at 2:30pm",
      //   reminder: true,
      // },
      // {
      //   id: 2,
      //   text: "Meeting at School",
      //   day: "March 3rd at 1:30pm",
      //   reminder: true,
      // },
      // {
      //   id: 3,
      //   text: "Food Shopping",
      //   day: "March 3rd at 10:00am",
      //   reminder: false,
      // },
    ]

  }
}
</script>

<style>
*{
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  font-family: Avenir, Helvetica, Arial, sans-serif;
}
.container{
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}

</style>
