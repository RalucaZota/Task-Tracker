

<script>
import Header from './components/Header.vue'
import Tasks from './components/Tasks.vue'
export default {
  name: "App",
  components: {
    Header,
    Tasks,
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
      ]
    }

  },
  created(){
    this.tasks
  },
  methods:{
    deleteTask(id) {
      if(confirm('Are you sure?'))
      this.tasks = this.tasks.filter((task) => task.id !== id)
    },
    toggleReminder(id) {
      console.log(id)
    }
  }
}
</script>

<template>

<Header title="Task tracker"/>
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
