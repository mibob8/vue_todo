<template>
  <div class="container">
    <HeaderComponent title="Tytuł nagłówka2"></HeaderComponent>
    <TasksComponent 
    @toggle-reminder='toggleReminder' 
    @delete-task='deleteTask' 
    :tasks="tasks">
  </TasksComponent>
  </div>
</template> 
<script> 

import HeaderComponent from './components/Header'
import TasksComponent from './components/Tasks'

export default {
  name: 'App',
  components: { 
    HeaderComponent,
    TasksComponent,
  },
  data(){
    return {
      tasks: [],
    }
  },
  methods:{
    deleteTask(id){
      this.tasks = this.tasks.filter((task) => task.id !== id)
    },
    toggleReminder(id){
      this.tasks = this.tasks.map((task) => task.id === id ?
       {...task, reminder: !task.reminder} : task)
    }
  },
  created(){
    this.tasks = [
      {
      id: 1,
      text: 'Lorem ipsum',
      day: '10.01.2023',
      reminder: false,
      },
      {
      id: 2,
      text: 'Lorem ipsum',
      day: '12.01.2023',
      reminder: true,
      },
      {
      id: 3,
      text: 'Lorem ipsum',
      day: '11.01.2023',
      reminder: false,
      },
  ]
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
