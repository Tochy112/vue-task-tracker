<template>
  <div class="container">
      
    <Header title="Task Tracker" />  
    <Tasks :tasks="task"/>

  </div>
</template>

<script>

import Header from './components/Header';
import Tasks from './components/Tasks';

export default {
  name: 'App',

  components: {
    Header,
    Tasks,
},

  data(){
    return{
      task: []
    }
  },

  created(){
    this.task = [
      {
        id: 1,
        text: "Doctors Appointment",
        day: "March 1st at 2:30pm",
        reminder: true,
      },
      {
        id: 2,
        text: "Meeting at School",
        day: "March 3rd at 1:30pm",
        reminder: true,
      },
      {
        id: 3,
        text: "Food Shopping",
        day: "March 3rd at 10:00am",
        reminder: false,
      },
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
