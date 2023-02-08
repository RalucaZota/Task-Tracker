<script>
import Button from './Button.vue'
export default {
  name: "header",
  components:{
    Button
  },
  props:{
    title: String,
  }
  
};
</script>
<template>
<header>
<h1>{{title}}</h1>
<Button text="Add task" color="green"></Button>

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