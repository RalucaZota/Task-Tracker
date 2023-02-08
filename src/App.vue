
<script>
import Header from './components/Header.vue'
import AddTask from './components/AddTask.vue'
import Tasks from './components/Tasks.vue'
export default {
  name: "App",
  components: {
    Header,
    Tasks,
    AddTask
  },
  data(){
    return{
      tasks: [
        {
          id:1, 
          text:'Doctor s appointment',
          day: 'march 1st at 2.30',
          reminder: true,
        },
          {
          id:2, 
          text:'meeting',
          day: 'feb 10st at 2.30',
          reminder: true,
        },
          {
          id:3, 
          text:'Shooping',
          day: 'april 20th at 10.30',
          reminder: false,
        }
      ],
          showAddTask: false
    }

  },
  // data(){
  //   return{
  //     showAddTask: false
  //   }
  // },
  created(){
    this.tasks
  },
  methods:{
    toggleAddTask(){
      this.showAddTask =!this.showAddTask
    },
     addTask(task) {
      this.tasks = [...this.tasks, task]
    },
    deleteTask(id) {
      if(confirm('Are you sure?'))
      this.tasks = this.tasks.filter((task) => task.id !== id)
    },
    toggleReminder(id) {
      this.tasks = this.tasks.map((task) => task.id === id ? {...task, reminder: !task.reminder} : task)
    },
   
  }
}
</script>

<template>

<Header @toggle-add-task="toggleAddTask" title="Task tracker" :showAddTask="showAddTask"/>
<div v-show="showAddTask">
<AddTask @add-task="addTask"/>
</div>
<Tasks  @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks="tasks"/>
</template>

<style >

/* @import "https://cdn.jsdelivr.net/npm/bulma@0.9.4/css/bulma.min.css"; */
.btn{
  display: inline-block;
  background-color: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
</style>
