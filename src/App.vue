<template>
  <div class="container">
    <Header/>
    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-on:deleteTodo= "deleteTodo($event)"  v-bind:todos= 'todos'/>
  </div>
</template>

<script>

import Header from './components/Header';
import Todos from './components/Todos';
import AddTodo from './components/AddTodo';

export default {
  name: 'App',
  components: {
    Todos,
    AddTodo,
    Header
  },
  data: () => {
    return {
      todos: [{
        id: '1',
      text: 'todo one',
      completed: false
    }, {
      id: '2',
      text: 'todo two',
      completed: true
    }]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => id !== todo.id)
    },
    addTodo(todo) {
      this.todos = [...this.todos, todo]
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  background-color: #F7F7FF;
}
.container {
  text-align: center;
}
</style>
