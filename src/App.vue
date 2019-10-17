<template>
  <div id="app">
    <div class="container">
      <h1>To Do List App with Vue</h1>
      <AddForm v-on:taskAdded="handleTask"></AddForm>
      <div class="empty" v-if="isEmpty">Your task list is empty now.</div>
      <TodoList v-bind:todos=todos></TodoList>
    </div>
  </div>
</template>

<script>
import AddForm from './components/AddForm'
import TodoList from './components/TodoList'
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      todos : [],
      isEmpty : true
    }
  },
  methods: {
    handleTask(task){
      this.isEmpty = false;
      this.todos.push(task);
    }
  },
  components : {
    AddForm,
    TodoList
  },
  

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.container{
  width:960px;
  margin: 0 auto;
}

.empty{
  margin-top: 20px;
}

</style>
