<script>
import Button from './Button.vue'
export default {
  name: "header",
  components:{
    Button
  },
  props:{
    title: String,
    showAddTask: Boolean
  }
  
};
</script>
<template>
<header>
<h1>{{title}}</h1>
<Button @toggle-add-task="$emit('toggle-add-task')"  text="Add task" color="green"></Button>

</header>
</template>
<style scoped>
header{
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  border: 1px solid red;
}
</style>