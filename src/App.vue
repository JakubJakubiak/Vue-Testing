<template>
  <div>
  
    <TodoApp />
  </div>
</template>


<script>
import Todo from './components/TodoApp.vue'
export default {
  components:{
    TodoApp :Todo
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

</style>
