<template>
  <div id="app">
    <Header />
    <Todos :todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>

import Todos from './components/Todos'
import Header from './components/layout/Header'

export default {
  name: 'App',
  components: {
    Todos,
    Header
  },
  data () {
    return {
      todos: [
        {
          id: 1,
          title: 'Learn Vue',
          completed: false
        },
        {
          id: 2,
          title: 'Do grocery shopping',
          completed: false
        },
        {
          id: 3,
          title: 'Clean the house',
          completed: false
        }
      ]
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id)
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
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}

</style>
